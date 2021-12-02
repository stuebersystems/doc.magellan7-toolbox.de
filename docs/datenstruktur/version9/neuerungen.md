# Änderungen der Datenstruktur von MAGELLAN 8 auf MAGELLAN 9

## Legende

**T** = Tabelle
**A** = Ansicht

## Neue Felder

Art | Name                   | Feldname             | Verweis auf      | Typ | Grösse | Position
--- | ---------------------- | -------------------- | ---------------- | --- | ------ | --------
T   | Schueler               | Fremdsprache1Erteilt |                  | S   |        | POSITION 124
T   | Schueler               | Fremdsprache2Erteilt |                  | S   |        | POSITION 131
T   | Schueler               | Fremdsprache3Erteilt |                  | S   |        | POSITION 138
T   | Schueler               | Fremdsprache4Erteilt |                  | S   |        | POSITION 145
T   | Sorgeberechtigte       | Geschlecht           |                  | A   | 1      | POSITION 17
A   | SchuelerFamilie        | Geschlecht           |                  | A   | 1      | POSITION 24
T   | AchievementProfiles    | Position             |                  | S   |        | POSITION 15
