# View SchuelerAbwesenheiten

Grundlage ist die Tabelle:

* [SchuelerFehlzeiten](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/SchuelerFehlzeiten/).

| Feldname  | Typ | Größe | Funktion | Bemerkung                                |
|-----------|-----|-------|----------|------------------------------------------|
| Mandant   | I   | -     | -        | -                                        |
| ID        | I   | -     | -        | -                                        |
| Schueler  | I   | -     | -        | -                                        |
| Von       | D   | -     | -        | -                                        |
| Bis       | D   | -     | -        | -                                        |
| Grund     | A   | 20    | V        | Verweis auf Tabelle **SchuelerFehlgruende** |
| Bemerkung | M   | -     | -        | -                                        |
