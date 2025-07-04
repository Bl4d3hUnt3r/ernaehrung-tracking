# Ernährungstracking

Hier werden tägliche Trackingdaten gepflegt, z. B. als `tracking.csv` oder `tracking.xlsx`.

- Zeitformat: ISO (Datum + Uhrzeit), z. B. `2025-07-03 08:15`
- Eine Zeile = eine Mahlzeit oder Snack
- Tagesgrenze: 18:00 Uhr

**Raw-Link zur aktuellen Datei** (zum Einlesen durch GPT):  
https://raw.githubusercontent.com/Bl4d3hUnt3r/ernaehrung-tracking/refs/heads/main/daten/tracking.csv

### Nutzung mit ChatGPT – Kontext & Logik

Dieses Tracking folgt einem **Tagesstart um 18:00 Uhr**, d. h. ein Ernährungstag reicht von 18:00 Uhr bis 17:59 Uhr des Folgetags. Die Spalte `id` dient zur eindeutigen Tageszuordnung (z. B. `2025-07-03` für den Tag ab 02.07., 18:00 Uhr).

ChatGPT übernimmt das strukturierte Erfassen der Mahlzeiten nach folgenden Prinzipien:

- **Keine Mittelwerte komplexer Gerichte:** Mahlzeiten wie Salate oder Aufläufe werden **immer anhand der realen Zutaten** und Mengen berechnet, keine Näherung.
- **Zeitzuordnung:** Mahlzeiten werden grundsätzlich der **Uhrzeit der Eingabe** zugeordnet, es sei denn, du gibst eine andere Zeit explizit an.
- **Makro-Priorität:** Fokus auf **Proteinreichweite**, unter Einhaltung deines Tagesziels (z. B. 2100 kcal / 180–190 g Protein).
- **FDDB-basiert:** Alle Nährwertdaten werden primär mit **FDDB.de** abgeglichen, um maximale Genauigkeit zu gewährleisten.
- **Tracking-Ausgabe:** Am Ende jedes Tages generiert ChatGPT eine vollständige **CSV-kompatible Zeile pro Mahlzeit** sowie eine **Tagesbilanz**, welche direkt in die Datei eingefügt oder per Copy & Paste übernommen werden kann.
- **Verifizierte Historie:** Früher protokollierte Daten werden einzeln mit dir verifiziert und konsistent in die Datei übernommen.
- **Template-Validierung:** Die Struktur der Datei basiert dauerhaft auf [`tracking_template.csv`](./daten/tracking_template.csv) für volle Kompatibilität.
