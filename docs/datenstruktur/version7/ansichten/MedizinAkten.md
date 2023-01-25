# View MedizinAkten

Grundlage sind die Tabellen:

* [SchuelerMedizinAkten](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/SchuelerMedizinAkten/)
* [LehrerMedizinAkten](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/LehrerMedizinAkten/)
* [PersonenMedizinAkten](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/PersonenMedizinAkten/)

| Feldname       | Typ | Größe | Funktion | Bemerkung |
|----------------|-----|-------|----------|-----------|
| Mandant        | I   | -     | -        | -         |
| ID             | I   | -     | -        | -         |
| EnbreaID       | A   | 24    | -        | -         |
| Typ            | I   | -     | -        | -         |
| TypId          | I   | -     | -        | -         |
| TypBezeichnung | A   | 1     | -        | -         |
| Datum          | D   | -     | -        | -         |
| Behandlung     | M   | -     | -        | -         |
| Medikationen   | M   | -     | -        | -         |
| Bemerkung      | M   | -     | -        | -         |
