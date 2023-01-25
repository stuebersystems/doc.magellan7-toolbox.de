# View GroupMembers

Grundlage sind:

* [tblGroupMembers](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/tblGroupMembers/)
* [Groups](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/Groups/)
* [Personen](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/Personen/)
* [Lehrer](https://doc.magellan-toolbox.stueber.de/datenstruktur/ansichten/Lehrer/)
* [Schueler](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/Schueler/)
* [Sorgeberechtigte](https://doc.magellan-toolbox.stueber.de/datenstruktur/tabellen/Sorgeberechtigte/)

| Feldname           | Typ | Größe | Funktion | Bemerkung                                |
|--------------------|-----|-------|----------|------------------------------------------|
| Mandant            | I   | -     | PV       | Verweis auf Tabelle **Mandanten**        |
| ID                 | I+  | -     | P        | -                                        |
| EnbreaID           | A   | -     | -        | Externer Identifikator aus ENBREA        |
| Group              | I   | -     | V        | Verweis auf Tabelle **Groups**           |
| GroupCode          | A   | -     | -        | -                                        |
| GroupName          | A   | -     | -        | -                                        |
| MemberID           | I   | -     | V        | ID der jeweiligen Tabelle je nach Typ    |
| MemberType         | S   | -     | -        | Mögliche Werte:<br/>1 = Person<br/>2 = Lehrer<br/>3 = Schüler<br/>4 = Sorgeberechtigte |
| MemberFirstname    | A   | -     | -        | -                                        |
| MemberLastname     | A   | -     | -        | -                                        |
| MemberStreet       | A   | -     | -        | -                                        |
| MemberState        | A   | -     | -        | -                                        |
| MemberZipCode      | A   | -     | -        | -                                        |
| MemberCity         | A   | -     | -        | -                                        |
| MemberPhone        | A   | -     | -        | -                                        |
| MemberEmail        | A   | -     | -        | -                                        |
| StartedAt          | D   | -     | -        | -                                        |
| FinishedAt         | D   | -     | -        | -                                        |
| Contribution       | N   | -     | -        | -                                        |
| ContributionPaidOn | D   | -     | -        | -                                        |
| Function1          | A   | -     | -        | -                                        |
| Function2          | A   | -     | -        | -                                        |
