# LB3 Dokumentation - Kevin Lang

[TOC]

## K1 - Umgebung auf eigenem Notebook eingerichtet und funktionsfähig (4p.)

### VirtualBox
VM manuell erstellt
Name: M300.1
Typ: Linux (Ubuntu (64-bit))

VM kopiert von GitHub (Vagrant file)
Name: VagrantVMs_default_1551088078848_94350
Typ: Linux (Ubuntu (64-bit))
Speicherort: C:/Users/kevin/M300/vagrant/user

### Vagrant
Eingerichtet und über Git-Client verwendet

### Git-Client
Eingerichtet und gebraucht (Git Bash)

### SSH-Key für Client erstellt
MB SSH-Key: 49:ff:56:b6:2d:ea:a9:ae:7a:ba:fa:ae:e6:26:c4:ad
Überprüfbar unter: https://github.com/settings/keys


## K2 - Eigene Lernumgebung ist eingerichtet (5p.)
Übungsfolderpfad:
~/Documents/TBZ-Module/M300/MeinLokalesRepository/M300

### GitHub oder Gitlab-Account ist erstellt
Mein Github Account lautet: KevinLang76 (https://github.com/KevinLang76)

### Git-Client wurde verwendet
Git Bash für jegliche Einrichtungen gebraucht

### Dokumentation ist als Mark Down vorhanden
^^Ja

### Mark down-Editor ausgewählt und eingerichtet
HarooPad Mark Down editor verwendet.
HarooPad ist deshalb empfehlenswert, weil es Bearbeitungs und Preview Fenster gleichzeitig anzeigen kann und Formatbefehle in Optionen vordefinert ausgewählt werden kann.

### Mark down ist strukturiert
+ Reihenfolge aller Themen entspricht der von den Bewertungskriterien.
+ Automatisches Inhaltsverzeichniss

## K3 (5p.)
### Bestehenden Docker-Dontainer kombinieren
Für das einrichten von Docker habe ich folgende Anleitung verwendet:
https://www.tecmint.com/install-apache-web-server-in-a-docker-container/

### Kennt die Docker spezifischen Befehle
Auflistung meiner Meinung nach Wichtiger Befehlen:

| Befehl | Beschreibung |
|--------|--------|
|  docker attach |  Lokaler In-/Output an laufende Kontainer anhängen  |
|docker commit  | Erstellung eines neuen Image des aktuellen Kontainers|
|docker exec|Ausführung des Befehls auf laufendem Kontainer|
|docker info| Zeigt Systeminformationen an|
|docker ps|Auflistung aller Kontainer|
|docker search /name/|Suchfunktion für Images auf dem Docker Hub|
|docker pull /name/|Herunterladen des genannten Image|

### Funktionsweise getestet inkl. Dokumentation der Testfälle
Docker VM (apache) funktionstüchtig und in der Virtualbox ersichtlich: True
Apache Verzeichnis erstellt:
True
Apache Verzeichniss enthält HTML-Code der Standardwebseite:
True
Webseite über Host Maschine erreichbar:
False

### Projekt mit Git und Markdown dokumentiert
^^MarkDown


## K4 - Sicherheitspakete sind implementiert (5p.)
### Service-Überwachung ist eingerichtet
cAdvisor ist eingerichtet (als eigener Container)

### Aktive Benachrichtigung ist eingerichtet
durch cAdvisor:
~$ docker run -d --name cadvisor -v /:/rootfs:ro -v /var/run:/var/run:rw -v /sys:/sys:ro -v /var/lib/docker/:/var/lib/docker:ro -p 8080:8080 google/cadvisor:latest

### mind. 3 Aspekte der Container Absicherung sind berücksichtigt

- CPU und RAM begrenzen
>deploy:
resources:
limits:
cpus: '0.5'
memory: 240M

- Non-Root User erstellen:
Name: TUser
PW: Welcome2019
.
>~$ RUN groupadd -r user_grp && useradd -r -g user_grp user
~$ USER user

- Restart-Eigenschaft
>restart: always


### Sicherheitsmassnahmen sind dokumentiert (Bezug zur eingerichteten Umgebung ist vorhanden)

Siehe "mind. 3 Aspekte der Container Absicherung sind berücksichtigt"

### Projekt mit Git und Markdown dokumentiert
^^ Markdown

## K5 - Zusätzliche Bewertugnspunkte allegemein (5p.)
Kreativität, Komplezität, Umfang, Umsetzung

##### Reflexion
Ich hatte sehr mühe in diesem Modul. Sehr selten wusste ich wirklich wie ich vogehen soll. Ich habe viele Stunden in LB2 und LB3, auch Wochenends, investiert, hatte aber nie das Gefühl von Fortschritt. Ich habe deshalb auch kein ausführliches Dockerfile, sonder habe alles direkt manuell umgesetzt.
Ich hoffe das ich mit dem Modul M901 ab dem 15.5.2019 besser mit Linux umgehen kann.


## K6 - Zusätzliche systemtechnische Bewertungspunkte (4p.)
### Container-Infrastruktur
Gegeben
### Image-Bereitstellung
Images einmal auf Lokalen Ordner bereitgelegt:
~/.../Documents/TBZ-Module/M300/MeinLokalesRepository/M300/Images




