# PythonWerkstatt BG

Eine browserbasierte Lernumgebung für Schülerinnen und Schüler des beruflichen Gymnasiums. Das Portal führt in kleinen Schritten durch die Grundlagen der Programmierung mit Python und verbindet Erklärungen direkt mit ausführbaren Aufgaben.

![Übersicht der PythonWerkstatt](docs/screenshots/startseite-desktop.png)

## Enthalten

- 12 Lektionen vom ersten `print()` bis zu Funktionen, Listen und Fehlersuche
- 12 automatisch prüfbare Programmieraufgaben
- echter Python-Interpreter im Browser über Pyodide
- XP, Level, Lernfortschritt und acht Erfolge
- lokales Lernprofil ohne Server und ohne Übertragung personenbezogener Daten
- responsive Oberfläche für Computer, Tablet und Smartphone

## Lokal starten

Wegen des Web Workers muss die Seite über einen lokalen Webserver geöffnet werden:

```powershell
python -m http.server 4173
```

Danach `http://localhost:4173` öffnen.

## Technik

Das Projekt ist bewusst ohne Build-Schritt aufgebaut:

- `index.html` enthält die feste App-Struktur.
- `styles.css` enthält Layout und responsive Darstellung.
- `content.js` enthält Lektionen, Aufgaben und Erfolge.
- `app.js` steuert Navigation, Lernstand, Auswertung und UI.
- `python-worker.js` führt Python isoliert in einem Web Worker aus.

Der Lernstand wird ausschließlich im `localStorage` des verwendeten Browsers gespeichert.

## Dokumentation

- [Übergabe für die Weiterarbeit](UEBERGABE_Codex.md)
- [Didaktik, Datenschutz und Quellen](docs/TECHNIK_UND_DIDAKTIK.md)
