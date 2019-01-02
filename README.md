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

# 3. Anwendung

Nun ist der Container betriebsbereit und er kann verwendet werden.
So kann zum Beispiel mit den erstellten Shortcuts auf den Windows- oder den Web-Client zugegriffen werden.
Auch die Verbindung auf den SQL-Server im Container, sowie das Arbeiten mit VS-Code und AL sind von außerhalb möglich.


Weitere Informationen zu den einzelnen Punkten befinden sich im Wiki.
