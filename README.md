# MatchPlan Pro

Ein flexibles Framework zur Erstellung, Verwaltung und Analyse von Trainingsplänen für Sportler, Trainer und ambitionierte Amateure. Dieses Tool wurde entwickelt, um eine dynamische und visuell ansprechende Alternative zu statischen Tabellen zu bieten, die sofortiges Feedback zur Trainingsstruktur gibt.

## Übersicht

MatchPlan Pro ist eine reine Frontend-Anwendung, die es Benutzern ermöglicht, detaillierte wöchentliche Trainingspläne zu erstellen, den Fortschritt zu verfolgen und die Belastung zu analysieren. Die Anwendung ist auf Geschwindigkeit, Datenschutz und Flexibilität ausgelegt. Der gesamte Zustand wird primär lokal im Browser gespeichert, kann aber über eine einfache, anonyme URL über mehrere Geräte hinweg synchronisiert werden. Dies gibt dem Nutzer die volle Kontrolle über seine sensiblen Trainingsdaten, ohne dass ein Benutzerkonto notwendig ist.

## Kernfunktionen

* **Dynamische Wochenplanung:** Erstellen und bearbeiten Sie Wochenpläne intuitiv, indem Sie Trainingseinheiten über ein Menü zuweisen. Pläne sind nicht in Stein gemeißelt – passen Sie die Woche jederzeit an, um auf unvorhergesehene Ereignisse oder das eigene Körpergefühl zu reagieren.

* **Phasenbasierte Periodisierung:** Strukturieren Sie Ihr Training in bis zu vier Phasen (z.B. Grundlagen, Aufbau, Wettkampf, Tapering) mit jeweils eigenen, anpassbaren Zielen. Diese Funktion unterstützt das sportwissenschaftliche Prinzip der Periodisierung, indem sie hilft, die Belastung über einen Makrozyklus gezielt zu steuern und Leistungsspitzen zum richtigen Zeitpunkt zu erreichen.

* **Intensitäts-Management:**
    * **Visueller Index:** Ein Kuchendiagramm zeigt auf einen Blick die prozentuale Verteilung der Trainingskategorien (Training, Regeneration, Match, Pause). So lässt sich die Balance der Woche sofort erfassen.
    * **Belastungs-Score:** Ein zentraler Index (0-99) quantifiziert die wöchentliche Intensität. Dieses einfache, aber mächtige Werkzeug hilft, das Risiko von Übertraining zu minimieren und eine progressive Steigerung der Belastung sicherzustellen.
    * **Anpassbare Kategorien:** Definieren Sie eigene Trainingsarten (z.B. "Yoga", "Sprint-Training", "Technik-Drills") und weisen Sie diesen eine Intensitäts-Kategorie zu (Keine, Niedrig, Mittel, Hoch). Diese Flexibilität macht das Tool für praktisch jede Sportart und Trainingsphilosophie anwendbar.

* **Fortschritts-Tracking:**
    * Markieren Sie Einheiten als "erledigt" oder "verpasst", um eine ehrliche Bilanz der Trainingsdisziplin zu ziehen.
    * Fügen Sie detaillierte Kommentare und Notizen zu jeder Trainingseinheit hinzu, um subjektives Empfinden, besondere Vorkommnisse oder Leistungsdaten festzuhalten.
    * Verfolgen Sie Ihre Gewichtsentwicklung in einem separaten Diagramm, um die Auswirkungen des Trainings auf den Körper zu beobachten.

* **Synchronisation & Datenhoheit:**
    * **URL-basierte Synchronisation:** Erstellen Sie einen einzigartigen, teilbaren Link, um Ihren Plan auf mehreren Geräten (z.B. Desktop und Smartphone) zu laden und synchron zu halten. Änderungen werden nach Abschluss einer Bearbeitung automatisch hochgeladen. Ein Status-Indikator und ein manueller Sync-Button geben volle Kontrolle.
    * **Lokal & Privat:** Ihre Daten gehören Ihnen. Alle Informationen werden primär im Local Storage Ihres Browsers gespeichert. Die Online-Synchronisation ist optional.
    * **Manuelles Backup:** Sichern Sie Ihren kompletten Trainingsplan inklusive aller personalisierten Einstellungen und Fortschritte als JSON-Datei. Teilen Sie diese Datei mit Trainern, Teamkollegen oder nutzen Sie sie als Offline-Backup.

## Für wen ist dieses Framework?

* **Sportler (Amateure & Profis):** Zur eigenständigen, detaillierten Planung, Visualisierung und Analyse des eigenen Trainings. Ideal, um die eigene Entwicklung nachzuvollziehen und die Trainingssteuerung zu verbessern.
* **Trainer & Coaches:** Als Werkzeug, um standardisierte oder individuelle Trainingspläne für Athleten zu erstellen und diese einfach per Sync-Link oder JSON-Datei zu teilen. Athleten können den Plan importieren, ihren Fortschritt tracken und den kommentierten Plan zur Analyse an den Trainer zurücksenden.
* **Entwickler:** Als anpassbare und erweiterbare Codebasis für spezialisierte Trainings-Web-Apps in verschiedenen Sportarten. Der Code ist bewusst einfach gehalten (Vanilla JS), um einen leichten Einstieg zu ermöglichen.

## Technologie

* **HTML5**
* **CSS3** (mit **Tailwind CSS** für schnelles und responsives Styling)
* **Vanilla JavaScript (ES6+)** (keine Framework-Abhängigkeiten für maximale Portabilität)
* **Chart.js** für die visuelle und ansprechende Darstellung von Daten
* **jsonblob.com** als anonymer JSON-Speicher für die optionale Synchronisation

## Wie man startet

Die Anwendung startet bewusst mit einem leeren Plan, um Ihnen volle Flexibilität zu geben. Sie haben mehrere Möglichkeiten:

1.  **Manueller Aufbau:** Nutzen Sie den "Bearbeiten"-Modus, um Wochen hinzuzufügen und Ihre ersten Trainingseinheiten zu erstellen. Ideal für einen komplett individuellen Start.
2.  **Synchronisation per Link:** Öffnen Sie einen bestehenden Sync-Link auf einem neuen Gerät, um den Plan sofort zu laden und mit anderen Geräten synchron zu halten.
3.  **Import:** Laden Sie eine bestehende `*.json`-Datei, um einen vollständigen Plan als Ausgangspunkt zu nutzen.
