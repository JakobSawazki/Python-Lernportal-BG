# Übergabeprotokoll: PythonWerkstatt BG

Stand: 9. Juni 2026

## Projektziel

Öffentliches Lernportal für Schülerinnen und Schüler des nichtgewerblichen beruflichen Gymnasiums. Schwerpunkt ist BPE 5 „Grundlagen der Programmierung“ mit Python. Die Lernenden sollen verständliche Erklärungen lesen, unmittelbar selbst programmieren und über XP sowie Erfolge zum Weiterarbeiten motiviert werden.

## Ablage und Repository

- Windows-Pfad Gerät 1: `D:\Google Drive\Lehramt\Lernfelder\Python-Lernportal-BG`
- Erwarteter Pfad Gerät 2: `C:\Google Drive\Lehramt\Lernfelder\Python-Lernportal-BG`
- GitHub-Repository: `https://github.com/JakobSawazki/Python-Lernportal-BG`
- GitHub Pages: `https://jakobsawazki.github.io/Python-Lernportal-BG/`

Die private Materialsammlung liegt getrennt unter `...\Lernfelder\BPE5`. Sie enthält unter anderem Musterlösungen und wird absichtlich nicht in dieses öffentliche Repository kopiert.

Verbindliche fachliche Referenz:

- Datei: `bpe-5-grundlagen-der-programmierung-version-mit-python.zip`
- Materialstand: 31. Juli 2025
- Größe: 23.496.218 Byte
- SHA-256: `E1747DB487817A46AAD11B1A6A6CD7E71AEF5F49414BFDCEE8CFC940DA8CF460`
- Offizieller Download: `https://www.schule-bw.de/resolveuid/4bf04e3081af47f9aa0a7455778f3cbe`
- Soll-Ist-Abgleich: `docs/BPE5_ABGLEICH_2025.md`

## Aktueller Funktionsumfang

- Übersicht mit persönlichem nächsten Schritt und Lernstatistik
- fünf Lernetappen mit zwölf Lektionen
- zwölf Aufgaben mit editierbarem Python-Code
- automatische Prüfung von Ausgabe, Variablen und Funktionen
- Pyodide 0.29.4 in einem Web Worker
- Abbruch sehr langer Programme nach zehn Sekunden
- lokaler Name beziehungsweise Kürzel, XP, Level, Erfolge und Entwürfe
- Nachschlagebereich mit kompakten Syntaxmustern
- responsive Navigation und Tastaturbedienung

## Dateistruktur

| Datei | Verantwortung |
| --- | --- |
| `index.html` | App-Shell, Navigation, Profildialog |
| `styles.css` | gesamtes Design und responsive Regeln |
| `content.js` | Module, Lektionen, Aufgaben, Erfolge, Nachschlagekarten |
| `app.js` | Routing, Rendern, Lernstand, XP, Aufgabenprüfung |
| `python-worker.js` | Laden und Ausführen von Pyodide |
| `assets/python-lernraum.png` | Titelbild der Übersicht |
| `docs/TECHNIK_UND_DIDAKTIK.md` | Quellen, Datenschutz und didaktische Entscheidungen |
| `docs/BPE5_ABGLEICH_2025.md` | Abdeckung des offiziellen Kompetenzrasters und offene Ausbauschritte |

## Zustandsmodell

Der Schlüssel im Browser lautet `pythonwerkstatt-bg-v1`. Gespeichert werden:

- `name`
- `xp`
- `completedLessons`
- `completedExercises`
- `drafts`
- `activityDates`
- `lastLessonId`

Es gibt kein Backend und keine Synchronisation zwischen Geräten. Das ist für die erste datenschutzarme Version beabsichtigt.

## Inhalte bearbeiten

Neue Inhalte möglichst nur in `content.js` ergänzen. Jede Lektion verweist mit `practiceId` auf eine Aufgabe. Jede Aufgabe verweist mit `lessonId` zurück.

Prüfarten:

- `output`: normalisierte Textausgabe muss exakt passen.
- `outputNumber`: letzte Ausgabezeile wird als Zahl verglichen.
- `tests`: zusätzlicher Python-Testcode prüft Variablen oder Funktionen.

XP werden pro Lektion und Aufgabe nur einmal vergeben.

## Sinnvolle nächste Schritte

1. Struktogramme als durchgängige Darstellungsform ergänzen.
2. Den ikonischen Einstieg aus Lernfortschritt 1 didaktisch übertragen.
3. Geschachtelte Verzweigungen ausdrücklich behandeln und üben.
4. Die GUI-Inhalte aus Lernfortschritt 2 als optionales Zusatzmodul prüfen.
5. Weitere Aufgabenvarianten und kleine Transferaufgaben ergänzen.
6. Optional Export/Import des lokalen Lernstands als JSON ergänzen.
7. Vor einem Einsatz als Leistungsnachweis ein separates Prüfungsprojekt mit Authentifizierung und serverseitiger Speicherung planen.

## Grenzen

- Die Plattform ist derzeit ein Übungsportal, kein manipulationssicheres Prüfungssystem.
- Lernstände bleiben auf einem Browserprofil und lassen sich lokal verändern.
- Für Pyodide und Lucide ist beim ersten Laden eine Internetverbindung erforderlich.
- `input()` verwendet im Aufgabenbereich vorbereitete Eingabezeilen statt modaler Dialoge.

## Einstieg für einen neuen Codex-Chat

Empfohlener Startauftrag:

> Öffne `UEBERGABE_Codex.md` und prüfe anschließend `git status`, `README.md`, `content.js` und `app.js`. Das Projekt ist das öffentliche Python-Lernportal für BPE 5. Arbeite mit dem vorhandenen Stil weiter und veröffentliche Änderungen nach Prüfung wieder über GitHub Pages.
