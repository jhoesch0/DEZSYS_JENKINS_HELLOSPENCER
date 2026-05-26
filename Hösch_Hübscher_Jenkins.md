# MidEng GK8.3 CI/CD Pipelines in Jenkins

## Aufgabenstellung

Diese Aufgabe umfasst die Installation und Konfiguration einer Jenkins CI/CD-Pipeline, die über ein GitHub-Repository getriggert wird und eine selbst gewählte Applikation automatisch baut, testet und deployt – wahlweise lokal oder auf einem Server.

### Jenkins installieren & Setup

Wir haben jenkins von Docker gepullt und dann ausgeführt.

![](C:\Users\jonas\AppData\Roaming\marktext\images\2026-05-26-08-10-20-image.png)

Dann haben wir Jenkins entsperrt und einen Benutzer angelegt.

<img src="file:///C:/Users/jonas/AppData/Roaming/marktext/images/2026-05-26-08-14-03-WhatsApp%20Image%202026-05-26%20at%2008.13.31.jpeg" title="" alt="" width="593">

### Plugins installieren

Danach haben wir unter Einstellungen/Plugins die nötigen Plugins installiert.

<img src="file:///C:/Users/jonas/AppData/Roaming/marktext/images/2026-05-26-08-12-09-image.png" title="" alt="" width="569">

### Hello World

<img src="file:///C:/Users/jonas/AppData/Roaming/marktext/images/2026-05-26-08-17-13-image.png" title="" alt="" width="573">

<img src="file:///C:/Users/jonas/AppData/Roaming/marktext/images/2026-05-26-08-17-32-image.png" title="" alt="" width="584">

### GKV Pipeline

Wir haben einen Zeitplan mit `*****` hinzugefügt, der jede Minute nachsieht.

![](C:\Users\jonas\AppData\Roaming\marktext\images\2026-05-26-08-19-49-image.png)

![](C:\Users\jonas\AppData\Roaming\marktext\images\2026-05-26-08-20-14-image.png)

Wenn alles richtig eingetragen wurde, kann man nun über einen Git Commit die Pipeline starten.

<img src="file:///C:/Users/jonas/AppData/Roaming/marktext/images/2026-05-26-08-21-25-image.png" title="" alt="" width="521">
