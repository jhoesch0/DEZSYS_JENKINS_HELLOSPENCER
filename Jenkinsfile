pipeline {
    agent {
        docker {
            image 'python:3.11'
            args '-p 5556:5556'
        }
    }

    environment {
        APP_PORT = '5556'
        GITHUB_REPO = 'https://github.com/jhoesch0/DEZSYS_JENKINS_HELLOSPENCER'
    }

    stages {
        stage('Pre-Build Cleanup') {
            steps {
                sh 'pkill -f "python hello.py" || true'
            }
        }

        stage('Checkout') {
            steps {
                git branch: 'main', url: "${GITHUB_REPO}"
            }
        }

        stage('Build') {
            steps {
                sh '''
                    python -m pip install --upgrade pip
                    pip install flask requests pytest
                    if [ ! -f count.txt ]; then
                        echo "0" > count.txt
                    fi
                    chmod 666 count.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'python -m pytest tests/test_hello.py -v'
            }
        }

        stage('Run') {
            steps {
                sh '''
                    nohup python src/hello.py > app.log 2>&1 &
                    sleep 5
                    curl http://localhost:5556/api/hello
                '''
            }
        }

        stage('Test API') {
            steps {
                sh 'python tests/test_api.py'
            }
        }

        stage('Keep Alive') {
            steps {
                sh 'sleep infinity'
            }
        }
    }

    post {
        always {
            sh 'pkill -f "python src/hello.py" || true'
            cleanWs()
        }
    }
}