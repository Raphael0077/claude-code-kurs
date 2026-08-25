# Projekt: Claude-Code-Lernbegleiter (Webseite)

Dieses Dokument ist das Projektgedächtnis für Claude Code. Es fasst zusammen,
was dieses Projekt ist, wie es aufgebaut ist und was noch zu tun ist. Bitte vor
Änderungen kurz lesen.

## Was das ist

Eine einzelne, in sich geschlossene Webseite (`index.html`) als persönlicher
Lernbegleiter zum "Claude Code"-Kurs. Sie fasst **14 Kapitel** zusammen –
jedes mit:

1. einer Kurzfassung (2–3 Sätze),
2. einem einsatzbereiten Prompt zum Kopieren,
3. einer Multiple-Choice-Quizfrage zum Selbsttest.

Zielgruppe: Einsteiger ohne Programmierkenntnisse (der Besitzer selbst).
Sprache: Deutsch, Schweizer Schreibweise (ss statt ß).

## Aufbau der Datei

Alles steckt in **einer** Datei: `index.html` (HTML + CSS + JS inline, keine
externen Abhängigkeiten ausser Google Fonts "IBM Plex Sans"/"IBM Plex Mono").

- Der gesamte **Inhalt** liegt in einem JS-Array `const kapitel = [...]` im
  `<script>`-Block. Jeder Eintrag hat die Felder:
  - `t`  – Titel
  - `teaser` – kurzer Anrisstext (im zugeklappten Zustand sichtbar)
  - `s`  – Kurzfassung (HTML erlaubt, z. B. `<b>`)
  - `p`  – der Prompt zum Kopieren
  - `q`  – Quizfrage
  - `o`  – Array der Antwortoptionen
  - `c`  – Index der richtigen Antwort (0-basiert)
  - `e`  – Erklärung, die nach dem Antworten erscheint
- Die Kapitel-Karten, der Index oben und die Quiz-Logik werden per JS aus
  diesem Array erzeugt. **Zum Ändern von Texten/Prompts/Quiz nur das Array
  anfassen** – der Rest zieht automatisch nach.

## Design-Entscheidungen (bitte beibehalten)

- Look: hell, clean, ruhig. Akzentfarbe ein kräftiges Vermillion-Rot
  (`--accent: #df3222`), Schweizer/typografischer Stil.
- Voll themefähig: hell + dunkel über CSS-Variablen (`:root`,
  `prefers-color-scheme`, `[data-theme]`). Umschalter oben rechts.
- Funktionen: aufklappbare Kapitel (`<details>`), Kopier-Button pro Prompt,
  Quiz mit Richtig/Falsch-Markierung, Fortschrittsanzeige.
- Der Lesefortschritt ("erledigt"-Häkchen) wird per `localStorage` gespeichert –
  nur lokal im Browser des Nutzers, nicht serverseitig, nicht geräteübergreifend.

## Nächste Schritte / offene Punkte

1. **Auf GitHub Pages veröffentlichen** (Hauptziel). Empfohlener Weg mit
   Claude Code:
   - Neues öffentliches Repo anlegen, z. B. `claude-code-kurs`.
   - `index.html` in den Repo-Wurzelordner legen, committen, pushen.
   - GitHub Pages auf Branch `main`, Ordner `/ (root)` aktivieren.
   - Ergebnis-URL: `https://<DEIN-GITHUB-NAME>.github.io/claude-code-kurs/`
   - Wichtig: Die Startdatei MUSS `index.html` heissen (tut sie).
2. Optional: Inhalte verfeinern (Formulierungen, weitere Quizfragen).
3. Optional: eigene Domain, Favicon, Feintuning der Farben.

## Kontext zur Entstehung

Erstellt in einer Claude-Cowork-Sitzung. Inhalt sinngemäss nacherzählt aus dem
frei zugänglichen Kurs unter https://claude-code-kurs.netlify.app/ (kein
1:1-Kopieren). In der Cowork-Sitzung war kein direkter GitHub-Zugang verfügbar,
deshalb wird die Veröffentlichung bewusst nach Claude Code (lokal) verlagert,
wo GitHub sauber angebunden ist.
