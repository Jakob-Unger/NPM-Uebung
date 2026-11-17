# npm-Übung – Frontend-Setup mit npm, Sass, Bootstrap & BrowserSync

Dieses Projekt zeigt einen professionellen Frontend-Workflow (MEDT, HTL Krems):

- **npm** als Paketmanager und Taskrunner
- **Bootstrap 5** modular über **Sass** eingebunden (nur benötigte Module → kleinere CSS-Datei)
- **Bootstrap Icons** als Icon-Bibliothek
- **BrowserSync** als lokaler Entwicklungsserver mit automatischem Live-Reload

## Voraussetzungen

- [Node.js](https://nodejs.org/) **Version 18 oder höher** (prüfen mit `node -v`)
- npm (wird mit Node.js mitinstalliert, prüfen mit `npm -v`)
- [Git](https://git-scm.com/)

## Installation

1. Repository klonen:

   ```bash
   git clone <REPO-URL>
   ```

2. In den Projektordner wechseln:

   ```bash
   cd npm-uebung
   ```

3. Alle Abhängigkeiten installieren (legt den Ordner `node_modules/` an):

   ```bash
   npm install
   ```

4. CSS einmalig kompilieren:

   ```bash
   npm run scss:build
   ```

## Verwendung / Befehle

| Befehl               | Beschreibung                                                                  |
| -------------------- | ----------------------------------------------------------------------------- |
| `npm run scss:build` | Kompiliert `src/scss/style.scss` einmalig nach `dist/css/style.css` (minifiziert) |
| `npm run scss:watch` | Überwacht Änderungen an den SCSS-Dateien und kompiliert automatisch neu       |
| `npm run serve`      | Startet BrowserSync und lädt den Browser bei Änderungen an HTML/CSS neu        |
| `npm run dev`        | Startet `scss:watch` und `serve` gleichzeitig (empfohlen beim Entwickeln)     |

Nach `npm run dev` öffnet sich die Seite automatisch unter `http://localhost:3000`.
Jede Änderung an `index.html` oder `src/scss/style.scss` wird sofort im Browser sichtbar.

## Projektstruktur

```
npm-uebung/
├── src/
│   └── scss/
│       └── style.scss      # Eigene Variablen, Bootstrap-Module, Icons, eigene Stile
├── dist/
│   └── css/
│       └── style.css       # Kompiliertes CSS (wird von index.html eingebunden)
├── index.html              # Testseite mit Grid, Buttons und Icons
├── package.json            # Abhängigkeiten und npm-Scripts
├── .gitignore
└── README.md
```

## Abhängigkeiten

| Paket             | Typ             | Zweck                                      |
| ----------------- | --------------- | ------------------------------------------ |
| `bootstrap`       | dependency      | CSS/JS-Framework                           |
| `bootstrap-icons` | dependency      | Icon-Bibliothek für Bootstrap              |
| `sass`            | devDependency   | Offizieller Sass-Compiler                  |
| `browser-sync`    | devDependency   | Entwicklungsserver mit Live-Reload         |
| `npm-run-all`     | devDependency   | Startet mehrere npm-Scripts parallel       |

## Hinweise

- Der Ordner `node_modules/` ist in der `.gitignore` ausgeschlossen und wird mit `npm install` wiederhergestellt.
- Design-Anpassungen (z. B. `$primary`) werden am Anfang von `src/scss/style.scss` gemacht, **vor** dem Import der Bootstrap-Module.
