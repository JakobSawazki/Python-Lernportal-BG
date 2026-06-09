# Technik, Didaktik, Datenschutz und Quellen

## Didaktische Leitidee

Das Portal reduziert die Einstiegshürde durch kurze Lernschritte:

1. Eine konkrete Vorstellung oder Regel wird erklärt.
2. Ein kleines Codebeispiel macht die Regel sichtbar.
3. Eine Verständnisfrage prüft den Kern der Lektion.
4. Eine direkt zugeordnete Programmieraufgabe fordert eigenes Handeln.
5. Automatisches Feedback erlaubt mehrere Versuche ohne öffentliche Bewertung.

Die Reihenfolge orientiert sich an BPE 5: Sequenz, Variablen und Datentypen, Ein- und Ausgabe, Berechnungen, Alternativen, Wiederholungen, Funktionen und Modularisierung. Listen und Debugging sind als zugängliche Erweiterung angefügt.

## Datenschutz

Die Anwendung besitzt kein Backend. Name oder Kürzel, Fortschritt und Codeentwürfe werden ausschließlich im lokalen Browserspeicher abgelegt.

- Es werden keine Konten angelegt.
- Es werden keine Namen an einen eigenen Server übertragen.
- Ein Kürzel genügt; ein vollständiger Name ist nicht erforderlich.
- Beim Löschen der Website-Daten im Browser wird auch der Lernstand gelöscht.

Externe technische Ressourcen werden beim Laden direkt vom jeweiligen CDN abgerufen:

- Lucide für Symbole
- Pyodide für die Python-Laufzeit

Für einen späteren schulischen Produktivbetrieb kann man diese Dateien selbst hosten, um externe Abrufe vollständig zu vermeiden.

## Technische Architektur

Die Anwendung ist eine statische Single-Page-Anwendung ohne Framework und Build-System. Hash-Routing hält alle Unterseiten mit GitHub Pages kompatibel.

Python läuft über Pyodide in einem separaten Web Worker. Dadurch bleibt die Benutzeroberfläche während normaler Programmausführung bedienbar. Nach zehn Sekunden wird der Worker beendet und neu aufgebaut; so werden typische Endlosschleifen begrenzt.

Die Aufgabenprüfung verwendet je nach Lernziel:

- erwartete Standardausgabe,
- numerische Ausgabe mit Toleranz,
- Python-Assertions gegen Variablen oder Funktionen.

## Quellen

- Ministerium für Kultus, Jugend und Sport Baden-Württemberg: [Bildungsplan Informatik, nichtgewerbliche Berufliche Gymnasien](https://www.bildungsplaene-bw.de/In_OS_nichtTG)
- Landesbildungsserver Baden-Württemberg: [Materialien zum Bildungsplan Informatik an den nichtgewerblichen Beruflichen Gymnasien](https://www.schule-bw.de/faecher-und-schularten/mathematisch-naturwissenschaftliche-faecher/informatik/material/materialien-zum-neuen-bildungsplan-informatik-an-den-nichtgewerblichen-beruflichen-gymnasien)
- Landesbildungsserver Baden-Württemberg: [Grundlagen der Programmierung – Version mit Python, Stand 31.07.2025](https://www.schule-bw.de/resolveuid/4bf04e3081af47f9aa0a7455778f3cbe)
- Pyodide: [Using Pyodide in a web worker](https://pyodide.org/en/stable/usage/webworker.html)
- Lucide: [Lucide Icons](https://lucide.dev/)

Die lokale Referenzdatei liegt unter
`D:\Google Drive\Lehramt\Lernfelder\BPE5\bpe-5-grundlagen-der-programmierung-version-mit-python.zip`.
Das Archiv enthält das Kompetenzraster sowie die Ich-kann-Listen zu den
Lernfortschritten 1 bis 3. Diese Dokumente wurden inhaltlich gesichtet.
Es wurden keine Musterlösungen und keine privaten Originaldateien in das
öffentliche Projekt übernommen.

Der detaillierte Soll-Ist-Abgleich ist in
[`BPE5_ABGLEICH_2025.md`](BPE5_ABGLEICH_2025.md) dokumentiert.

## Bildnachweis

`assets/python-lernraum.png` wurde am 9. Juni 2026 mit dem integrierten OpenAI-Bildgenerator eigens für dieses Projekt erzeugt.

Verwendete Bildidee: heller schulischer Arbeitsplatz mit Laptop, Python-Code, Karten für Sequenz, Entscheidung und Schleife sowie ruhiger grüner Freifläche für den Seitentitel; ohne Personen und ohne Markenlogos.
