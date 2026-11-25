# Lern-App

Statische Web-App (GitHub Pages). Läuft auf Mac und iPhone, offline nach dem ersten Laden.

## Neue Inhalte hinzufügen (ohne die App zu ändern)
1. Claude erzeugt eine Datei `content/<fach>.json` im gleichen Format wie `content/steuerlehre.json`.
2. Datei in den Ordner `content/` legen.
3. In `content/index.json` beim Fach `"datei": "<fach>.json"` eintragen.
4. Committen und pushen – die App lädt die neuen Inhalte beim nächsten Öffnen.

## Datenformat (format 1)
- `themen[]`: `id`, `ast`, `titel`, `folien`, `art` (wissen/rechnen),
  `ansehen[]` (Blöcke `text` / `formel` / `tabelle` mit `zeilen` und optional `kopf`),
  `zuordnen` (Paare `[Begriff, Erklärung]`), `luecken` (Sätze mit `{{Lösung|Alternative}}`),
  `erklaeren` (`frage`, `kernpunkte[]`).
- `aufgaben[]` (Rechentraining): `id`, `thema`, `titel`, `text`, `antwort` (Zahl), `toleranz`, `einheit`, `weg[]`.
- `id`s nie umbenennen, sonst geht der Lernstand dieser Karte verloren.

## iPhone
Seite in Safari öffnen → Teilen → „Zum Home-Bildschirm“.

## Lernstand zwischen Mac und iPhone
Gemeinsame Datei: `lernstand.json` im iCloud-Ordner.
- Mac (Chrome): einmal „Vorhandene öffnen“ oder „Neu anlegen“, danach beim Start „Synchronisieren“ – speichert automatisch.
- iPhone: beim Start „Laden“, nach dem Lernen „Jetzt sichern“ → In Dateien sichern → iCloud → ersetzen.
- Beim Zusammenführen gewinnt pro Karte der zuletzt gelernte Stand.
