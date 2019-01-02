# Nav on Docker

Dies ist ein Leitfaden zur Erstellung von Docker-Containern mit der Business Central Anwendung aus von Microsoft zur Verfügung gestellten Images auf einem Windows-Rechner.

Inhalt:
1)  Vorbereitung
2)  Container erstellen
3)  Container verwenden


# 1. Vorbereitung

Zunächst müssen wir die "Docker for Windows"-Anwendung installieren. Diese bekommen wir von der Docker Internetseite.
Nach der Installation müssen wir sichergehen, dass Docker für Windows-Container eingestellt ist.
Anschließend installieren wir noch das PowerShell-Modul "Navcontainerhelper", welches die Arbeit mit NavContainern erleichtert.

# 2. Container erstellen

Aufruf des navcontainerhelper-Befehls "new-navcontainer" um einen neuen Container zu erstellen.
Die möglichen Parameter sind auf der GitHub Seite des navcontainerhelper-repositorys zu finden.

Dieser Befehl führt eine Reihe von Schritten aus, die an einem Beispiel erläutert werden.

Bsp.:

new-navcontainer -accept_eula -containerName BConprem -UseBestContainerOS -includeCSide -doNotExportObjectsToText -shortcuts Desktop -imageName mcr.microsoft.com/businesscentral/onprem:13.1.25940.0

Schritt 1:
Ausgabe der Versionsnummer des Hosts, des Docker Clients und des Docker Servers.

Schritt 2:
Die Verfügbarkeit des im Parameter "imageName" angegebenen Images überprüfen und falls dieses noch nicht lokal vorhanden ist dieses aus dem entsprechenden Repository auf DockerHub beziehen.

Schritt 3:
Überprüfen ob schon ein Container mit dem durch den Parameter "containerName" festgelegtem Namen existiert, falls ja wird dieser jetzt enfernt.
(Es gibt hierfür keine extra Abfrage)

Schritt 4:
Durch den Parameter "UseBestContainerOS" sucht die Funktion ein Betreibssystem für den Container, das am Besten mit dem Betriebsystem des Hosts harmoniert. Wenn ein Image mit solch einem Betriebsystem gefunden wurde wird nun dieses verwendet.

Schritt 5:
Erstellen des Containers und Installation der benötigten Komponenten.

Schritt 6:
Starten des lokalen SQL-Servers und des Internet Information Servers.

Schritt 7:
Kopieren der Dateien in den Container.

Schritt 8:
Einrichtung der Anwendung aufgrund der in den Skripten hinterlegten Informationen.

Schritt 9:
Ausgabe der Verbindungsdaten zum Container

Schritt 10:
Erstellen der mit dem Parameter "shortcuts" geforderten Verknüpfungen auf dem Desktop

# 3. Anwendung

Nun ist der Container betriebsbereit und er kann verwendet werden.
So kann zum Beispiel mit den erstellten Shortcuts auf den Windows- oder den Web-Client zugegriffen werden.
Auch die Verbindung auf den SQL-Server im Container, sowie das Arbeiten mit VS-Code und AL sind von außerhalb möglich.
