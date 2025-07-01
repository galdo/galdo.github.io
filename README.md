# 📋 Interaktiver Trainingsplan – Dokumentation

---

## 1. 📘 Anwenderdokumentation

### 🏁 Übersicht

Der **Interaktive Trainingsplan** hilft dir, dein Tennis-Training strukturiert aufzubauen, Wochenziele zu verfolgen und deinen Fortschritt (inkl. Gewicht) visuell darzustellen. Die Anwendung läuft im Browser und speichert deine Daten lokal – kein Login nötig.

---

### 🗂️ Phasenauswahl

- Oben links findest du vier farbige Buttons für die Trainingsphasen:
  - 🟦 **1. Grundlagen**
  - 🟨 **2. Präzision**
  - 🟧 **3. Matchpraxis**
  - 🟥 **4. Turnierfokus**
- Klick auf eine Phase bringt dich direkt zur ersten Woche dieser Phase.

![Phasen-Buttons](screenshots/phasenauswahl.png)

---

### 📆 Wochen-Navigation

- Mit ← und → navigierst du zwischen den Wochen.
- Die aktuelle Woche wird oben angezeigt, z. B. „Woche 3 / 44“.
- ✏️ **Bearbeitungsmodus aktivieren** zum Ändern der Inhalte.

![Wochen-Navigation](screenshots/wochen-navigation.png)

---

### 🧱 Trainingsplan pro Woche

- Jeder Tag der Woche (Mo–So) hat eine eigene Karte mit:
  - 📅 Datum
  - 🏋️ Trainingstyp (mit Emoji)
  - 📝 Kurzbeschreibung
- Klick auf eine Karte zeigt Details:
  - ✅ Checkbox „Erledigt“
  - 💬 Kommentar
  - ⚖️ Gewichtseingabe (nur Sonntag)

---

### ✍️ Bearbeiten des Trainingsplans

- Aktiviere den Bearbeitungsmodus ✏️
- Klick auf eine Karte öffnet ein Formular:
  - 📌 Wochentag
  - 🏷️ Trainingsart
  - 😀 Icon (Emoji)
  - 📝 Kurzbeschreibung
  - 📖 Langbeschreibung (Markdown möglich)
- 🗑️ Einheiten löschen über Papierkorb-Symbol
- Änderungen werden sofort gespeichert (LocalStorage).

---

### 📊 Fortschritt & Gewicht

- Tabelle zeigt: ✅ durchgeführt / ❌ verpasst / ⏳ offen
- Gewichtsentwicklung (⚖️) wird als Liniendiagramm visualisiert (Chart.js)
- Diagramme passen sich dynamisch an deine Eingaben an

![Fortschrittsübersicht](screenshots/fortschritt.png)

---

### 💾 Datenimport & Backup

- Über 🔁 Symbol erreichst du:
  - 📤 Export deines aktuellen Plans (JSON-Datei)
  - 📥 Import einer Sicherung (ersetzt vorhandene Daten)
- Sicherungsdateien werden lokal gespeichert

---

## 2. ⚙️ Technische Dokumentation

---

### 🧩 Funktionsübersicht

| Funktion | Beschreibung | Icon |
|----------|--------------|------|
| `init()` | Startet die Anwendung und lädt Daten aus dem Speicher | <i class="fa-solid fa-play"></i> |
| `loadState()` / `saveState()` | Verwaltet das Speichern und Laden im `localStorage` | <i class="fa-solid fa-database"></i> |
| `renderAll()` | Render-Prozess für Wochenanzeige, Charts, Statistik | <i class="fa-solid fa-arrows-rotate"></i> |
| `renderPhase()` | Zeigt aktuelle Phase visuell an | <i class="fa-solid fa-layer-group"></i> |
| `renderWeek()` | Generiert die Tageskarten der Woche | <i class="fa-solid fa-calendar-week"></i> |
| `renderStatistics()` | Aktualisiert Fortschrittstabelle | <i class="fa-solid fa-table"></i> |
| `renderChart()` / `renderWeightChart()` | Erstellt die Diagramme mit Chart.js | <i class="fa-solid fa-chart-pie"></i>, <i class="fa-solid fa-chart-line"></i> |
| `handlePhaseClick()` etc. | Diverse Event-Handler für UI-Aktionen | <i class="fa-solid fa-hand-pointer"></i> |
| `showModal() / hideModal()` | Öffnen und Schließen von Dialogfenstern | <i class="fa-solid fa-window-maximize"></i> |

---

### 🧱 Datenmodell (Textbeschreibung)

Das Datenmodell basiert auf einer lokalen JSON-Struktur und besteht aus folgenden Komponenten:

- **Version**: Datenmodell-Version zur Migration (aktuell v3)
- **Startdatum**: Zeitpunkt, ab dem der Trainingsplan beginnt
- **Trainingseinträge**: Für jeden Tag können Trainingseinheiten mit Status (erledigt, Kommentar, Gewicht) hinterlegt werden
- **Wochenspezifische Trainingspläne**: Jede Woche enthält eine Liste von 7 Tagesplänen, jeweils mit Trainingsart und Beschreibung
- **Trainingsarten**: Ein Set von Trainingsarten (z. B. Kraft, Ausdauer), jede mit Icon, Kurz- und Langbeschreibung

---

### 🧩 UI-Elemente – Tabelle

| UI-Element                 | Selektor/ID                  | Funktion                             | Icon |
|---------------------------|------------------------------|--------------------------------------|------|
| Hauptcontainer            | `#app`                       | Enthält die komplette App            |      |
| Phasenauswahl             | `#phase-selector`            | Umschalten der Trainingsphasen       | <i class="fa-solid fa-layer-group"></i> |
| Wochenanzeige             | `#current-week-display`      | Zeigt aktuelle Woche/Daten an        | <i class="fa-solid fa-calendar-week"></i> |
| Navigation                | `#prev-week-btn`, `#next-week-btn` | Blättert durch Wochen            | ← / → |
| Trainingskarten           | `.training-card`             | Darstellung der Wochentage           |      |
| Bearbeiten-Button         | `#edit-mode-toggle-btn`      | Wechsel in Editiermodus              | ✏️ / ✔️ |
| Fortschrittstabelle       | `#stats-table-body`          | Übersicht Trainingsstatus            | <i class="fa-solid fa-table"></i> |
| Gewichtskurve             | `#weight-curve-chart`        | Line-Chart mit Gewichtsdaten         | <i class="fa-solid fa-chart-line"></i> |
| Import/Export             | `#import-export-btn`         | Öffnet Modal für Backup/Import       | <i class="fa-solid fa-rotate"></i> |

---

### 🧭 UI-Elementstruktur – Hierarchie

<body> └── div#app.container └── main ├── div#phase-selector-container │ └── div#phase-selector │ ├── button[data-phase="1"] │ ├── button[data-phase="2"] │ └── … └── div#content-area └── div.grid ├── div.left-column │ ├── ul#phase-goals │ ├── canvas#weeklyFocusChart │ └── … └── div#right-content-column ├── div.week-navigation │ ├── button#prev-week-btn │ ├── h3#current-week-display-wrapper │ └── button#next-week-btn ├── div#weekly-plan │ └── div.training-card ×7 ├── table.stats-table │ └── tbody#stats-table-body └── canvas#weight-curve-chart ```