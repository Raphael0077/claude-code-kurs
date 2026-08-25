# Claude-Code-Lernbegleiter

Eine kleine Webseite, die den "Claude Code"-Kurs in 14 Kapiteln zusammenfasst –
jedes Kapitel mit Kurzfassung, einem Prompt zum Kopieren und einer Quizfrage.

Die ganze Seite ist eine einzige Datei: **`index.html`**. Einfach im Browser
öffnen (Doppelklick) zum Anschauen.

## Mit Claude Code weiterbearbeiten

1. Diesen Ordner entpacken.
2. Ein Terminal in diesem Ordner öffnen und `claude` starten.
3. Claude Code liest die Datei `CLAUDE.md` automatisch und kennt damit den
   ganzen Projektkontext. Du kannst dann z. B. sagen:
   - „Veröffentliche diese Seite auf GitHub Pages."
   - „Ändere in Kapitel 3 die Quizfrage."
   - „Mach die Akzentfarbe etwas dunkler."

## Auf GitHub Pages veröffentlichen (Kurzform)

Am einfachsten sagst du Claude Code direkt: **„Leg ein öffentliches GitHub-Repo
an, pushe die index.html und aktiviere GitHub Pages."**

Manuell über die GitHub-Webseite:
1. Neues öffentliches Repo erstellen (z. B. `claude-code-kurs`).
2. `index.html` hochladen und committen.
3. Settings → Pages → Branch `main`, Ordner `/ (root)` → Save.
4. Nach 1–2 Minuten ist die Seite unter
   `https://<DEIN-NAME>.github.io/claude-code-kurs/` erreichbar.

## Inhalte ändern

Alle Texte, Prompts und Quizfragen stehen gesammelt im Array `const kapitel`
ganz im `<script>`-Teil der `index.html`. Nur dort anpassen – der Rest der Seite
baut sich daraus automatisch.
