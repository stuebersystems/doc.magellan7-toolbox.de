# Tabelle FachtafelFaecher

| Feldname              | Typ | Größe | Funktion | Bemerkung                                |
|-----------------------|-----|-------|----------|------------------------------------------|
| Mandant               | I   | -     | PV       | Verweis auf Tabelle **Mandanten**        |
| ID                    | I+  | -     | P        | -                                        |
| Fachtafel             | A   | 20    | V        | Verweis auf Tabelle **Fachtafeln**       |
| Fach                  | I   | -     | V        | Verweis auf Tabelle **Faecher**          |
| Unterrichtsart        | A   | 20    | V        | Verweis auf Tabelle **Unterichtsarten**  |
| Fachstatus            | A   | 20    | V        | Verweis auf Tabelle **Fachstati**        |
| Schwerpunkt           | A   | 20    | V        | Verweis auf Tabelle **Fachschwerpunkte** |
| Niveau                | A   | 20    | V        | Verweis auf Tabelle **Fachniveaus**      |
| KursNr                | S   | -     | -        | -                                        |
| Faktor                | N   | -     | -        | -                                        |
| Position              | S   | -     | -        | -                                        |
| Merkmal               | A   | 8     | -        | -                                        |
| Lehrer                | I   | -     | V        | Verweis auf Tabelle **Lehrer**           |
| Zusatzklasse          | I   | -     | V        | Verweis auf Tabelle **Klassen**          |
| IstStammkurs          | A   | 1     | -        | -                                        |
| Endnote1Fortschreiben | A   | 1     | -        | -                                        |
| Soll                  | N   | -     | -        | Sollstunden (=SollausdaVinci)            |
| Angleichung           | N   | -     | -        | Angleichung (=Angleichung aus daVinci)   |
| Bemerkung             | M   | -     | -        | -                                        |
| Hauptfach             | I   | -     | V        | Verweis auf Tabelle **Faecher**<br/>Übergeordnetes Fach des Feldes „Fach“ |
| Pflichtkurse          | A   | 20    | V        | Pflichtkurse bei Fachwahl                |
| HJ1_Gewaehlt          | A   | 20    | V        | E1 gewählt bei Fachwahl                  |
| HJ2_Gewaehlt          | A   | 20    | V        | E2 gewählt bei Fachwahl                  |
| HJ3_Gewaehlt          | A   | 20    | V        | Q1 gewählt bei Fachwahl                  |
| HJ4_Gewaehlt          | A   | 20    | V        | Q2 gewählt bei Fachwahl                  |
| HJ5_Gewaehlt          | A   | 20    | V        | Q3 gewählt bei Fachwahl                  |
| HJ6_Gewaehlt          | A   | 20    | V        | Q4 gewählt bei Fachwahl                  |
| Bilingual             | A   | 20    | V        | Verweis auf Tabelle **Kurssprachen**     |
| Q1Bilingual           | A   | 20    | V        | Verweis auf Tabelle **Kurssprachen**     |
| Q2Bilingual           | A   | 20    | V        | Verweis auf Tabelle **Kurssprachen**     |
| Q3Bilingual           | A   | 20    | V        | Verweis auf Tabelle **Kurssprachen**     |
| Q4Bilingual           | A   | 20    | V        | Verweis auf Tabelle **Kurssprachen**     |
| Leistungsart          | A   | 20    | V        | Verweis auf Tabelle **Leistungarten**    |
