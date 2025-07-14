# 📊 Ernährungstracking

Hier werden tägliche Trackingdaten gepflegt, z. B. als `tracking.csv` oder `tracking.xlsx`.

- Zeitformat: ISO (Datum + Uhrzeit), z. B. `2025-07-03 08:15`
- Eine Zeile = eine Mahlzeit oder Snack
- Tagesgrenze: **18:00 Uhr** → der neue Tag startet immer um 18:00 Uhr
- Grundlage ist das Template: [`tracking_template.csv`](./daten/tracking_template.csv)

**Raw-Link zur aktuellen Datei (für GPT):**  
https://raw.githubusercontent.com/Bl4d3hUnt3r/ernaehrung-tracking/refs/heads/main/daten/tracking.csv

---

## ✅ Logik & Regeln für ChatGPT

Dieses Tracking folgt einem **Tagesstart um 18:00 Uhr**  
(z. B. `20250703` für alle Einträge ab 02.07.2025, 18:00 Uhr bis 03.07.2025, 17:59 Uhr).

ChatGPT übernimmt das strukturierte Erfassen der Mahlzeiten nach diesen **fest definierten Prinzipien**:

- **Keine Näherungen oder Durchschnittswerte**  
  Alle Nährwertdaten werden **immer live recherchiert** – bevorzugt über **FDDB.de**, OpenFoodFacts oder offizielle Herstellerangaben.  
  Schätzungen oder pauschale Daten sind ausdrücklich **nicht zulässig**.

- **Rezept-basierte Mahlzeiten**  
  Komplexe Gerichte (z. B. Aufläufe, Salate) werden **immer anhand der realen Zutaten** (inkl. Marken & exakten Mengen) einzeln kalkuliert.

- **Zeitzuordnung**  
  Wenn keine Uhrzeit angegeben wird, gilt die Uhrzeit der Eingabe.  
  Eine andere Uhrzeit kann jederzeit explizit vorgegeben werden.

- **Makronährstoff-Priorität**  
  Fokus auf Proteinreichweite (Ziel: ~180–190 g Protein pro Tag bei ca. 2100 kcal).

- **CSV-Format (verbindlich)**  
  Jede Mahlzeit wird als einzelne Zeile exportiert, exakt nach diesem festen Aufbau:
TAG-ID;Datum;Uhrzeit;Mahlzeit;Lebensmittel / Beschreibung;Menge (g);kcal;Protein (g);KH (g);Zucker (g);Fett (g)

- **Verifizierte Historie**  
Bereits dokumentierte Tage und Mahlzeiten werden mit dir abgestimmt, um volle Nachvollziehbarkeit sicherzustellen.

- **Commit-Workflow**  
Am Tagesende liefert ChatGPT alle neuen Zeilen gebündelt, sodass sie als Block in `tracking.csv` übernommen werden können.

---

## 📌 Hinweis

- Die Tagesgrenze um 18:00 Uhr bestimmt die `TAG-ID`.
- Transparenz & Nachvollziehbarkeit sind Pflicht: Alle Nährwerte werden mit Quellen dokumentiert.
- Änderungen bei Marken, Mengen oder Rezepturen werden immer explizit festgehalten.
- Keine Automatisierung ohne finale Freigabe: Du entscheidest immer, was in die Datei übernommen wird.

---