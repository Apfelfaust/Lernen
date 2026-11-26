# Lern-App

Statische Web-App (GitHub Pages). Läuft auf Mac und iPhone, offline nach dem ersten Laden.

## Neue Inhalte hinzufügen (ohne die App zu ändern)
1. Claude erzeugt `content/<fach>.json` im Format von `content/steuerlehre.json`.
2. Datei in `content/` legen, in `content/index.json` beim Fach `"datei": "<fach>.json"` eintragen.
3. Committen und pushen – neue Inhalte erscheinen beim nächsten Öffnen.

## Datenformat (format 2)
- `themen[]`: `id`, `ast`, `titel`, `folien`, `art` (wissen/rechnen), `relevanz` (kern/mittel),
  `ansehen[]` (Blöcke `text`, `formel`, `tabelle` mit `zeilen` [Begriff, Text, optional "fall:<id>"] und `kopf`, `bild` mit `src` in content/ und `alt`),
  `puzzle[]` (Bausteine fürs Mindmap-Puzzle), `karten[]`.
- Karte: `id`, `titel`, `frage`, `kernpunkte[]`, optional `zuordnen` ([Begriff, Erklärung]) und `luecken` (Sätze mit `{{Lösung|Alternative}}`).
  Fehlt `zuordnen` oder `luecken`, wird die Stufe übersprungen.
- Fall: `typ: "fall"`, `id`, `titel`, `folien`, `sachverhalt`, `frage`, `loesung` ([Schritt, Text]), `ergebnis`, optional `merke`.
- `aufgaben[]`: `id`, `thema`, `titel`, `text`, optional `anlage`, `antwort` (Zahl), `toleranz`, `einheit`, `weg[]`.
- `id`s nie umbenennen, sonst geht der Lernstand dieser Karte verloren.

## Lernstand zwischen Mac und iPhone
Gemeinsame Datei `lernstand.json` im iCloud-Ordner.
- Mac (Chrome): einmal „Vorhandene öffnen“ oder „Neu anlegen“, danach beim Start „Synchronisieren“ – speichert automatisch.
- iPhone: beim Start „Laden“, nach dem Lernen „Jetzt sichern“ → In Dateien sichern → iCloud → ersetzen.

## iPhone
Seite in Safari öffnen → Teilen → „Zum Home-Bildschirm“.
