# DarkWings Tournament Analytics — Preview 0.1

Neues, eigenständiges Analyse-Dashboard. Importiert öffentliche Ravensburger-Runden und ermittelt für drei manuell zugeordnete Phasen deduplizierte Spieler und bekannte Farbkombinationen. Zeigt Teilnehmer, Deckverteilung, Day-1→Day-2- und Day-2→Top-Cut-Conversion und exportiert CSV.

## Wichtige Grenzen
- Die Turnierphasen müssen derzeit manuell zugeordnet werden. Das Tool erfindet keine Top 32, wenn nur eine Top-8-Runde vorhanden ist.
- Ob die Deckfarben über die öffentliche Ravensburger-Match-API tatsächlich verfügbar sind, muss anhand eines Live-Abrufs geprüft werden. Die UI weist fehlende Deckfarben ausdrücklich aus.
- Das Tool liest ausschließlich öffentliche Daten. Keine InkDecks-Abfragen, kein Scouting, keine Team-Beobachtungsdatenbank.
- Ein Spieler zählt pro ausgewählter Runde genau einmal. Ein Teilnehmer der ersten Day-1-Runde ist nicht notwendigerweise identisch mit der offiziellen Anzahl registrierter Spieler.
- Die alte InkScout-App wird nicht automatisch überschrieben.

## Lokaler Start
`npm install` → `npm run dev`; Netlify Functions funktionieren erst über Netlify oder `netlify dev`.

## Deployment ohne Ordner-Chaos
Empfohlen: **neue Netlify-Site mit neuem GitHub-Repository**, dessen Root diese Dateien enthält. Alternativ die Dateien im aktuell als Base Directory konfigurierten Ordner `inkscout 4` ersetzen und dessen `netlify/functions` ebenfalls aktualisieren. Alte InkScout-Funktionen können dort verbleiben, werden aber nicht aufgerufen. Build: `npm run build`, Publish: `dist`, Functions: `netlify/functions`.
