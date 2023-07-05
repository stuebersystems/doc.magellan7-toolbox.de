# Tabelle SchuelerFachdaten

| Feldname               | Typ | Größe | Funktion | Bemerkung                                |
|------------------------|-----|-------|----------|------------------------------------------|
| Mandant                | I   | -     | PV       | Verweis auf Tabelle **Mandanten**        |
| ID                     | I+  | -     | P        | -                                        |
| Schueler               | I   | -     | V        | Verweis auf Tabelle **Schueler**         |
| Klasse                 | I   | -     | V        | Verweis auf Tabelle **Klassen**          |
| Zeitraum               | I   | -     | V        | Verweis auf Tabelle **Zeitraeume**       |
| SchuelerZeitraumID     | I   | -     | PV       | Verweis auf Tabelle **SchuelerZeitraeume** |
| Fach                   | I   | -     | V        | Verweis auf Tabelle **Faecher**          |
| Unterrichtsart         | A   | -     | V        | Verweis auf Tabelle **Unterrichtsarten** |
| Fachstatus             | A   | -     | V        | Verweis auf Tabelle **Fachstati**        |
| Schwerpunkt            | A   | -     | V        | Verweis auf Tabelle **Fachschwerpunkte** |
| Niveau                 | A   | -     | V        | Verweis auf Tabelle **Fachniveaus**      |
| KursNr                 | S   | -     | -        | -                                        |
| Beurteilung            | M   | -     | -        | -                                        |
| Note1                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Schriftl. Note 1`|
| Note2                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Schriftl. Note 2`|
| Note3                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Schriftl. Note 3`|
| Note4                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Schriftl. Note 4`|
| Note5                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Mdl. Note`|
| Note6                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote1`|
| Note7                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote2`|
| Note8                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote3`|
| Note9                  | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote4`|
| Note10                 | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote5`|
| Note11                 | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote6`|
| Note12                 | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote7`|
| Note13                 | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote8`|
| Note14                 | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Zusatznote9`|
| Vornote                | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Vornote`
| Endnote1               | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Endnote`|
| Endnote2               | I   | -     | V        | Verweis auf Tabelle **Noten**<br/>Name in der Oberfläche: `Endnote gesamt`|
| Faktor                 | N   | -     | -        | -                                        |
| Position               | S   | -     | -        | -                                        |
| Merkmal                | A   | 8     | -        | -                                        |
| Lehrer                 | I   | -     | V        | Verweis auf Ansicht **Lehrer**           |
| ZusatzKlasse           | I   | -     | V        | Verweis auf Tabelle **Klassen**          |
| IstStammkurs           | A   | 1     | -        | -                                        |
| Endnote1Fortschreiben  | A   | 1     | -        | -                                        |
| Mahnung                | S   | -     | -        | Mögliche Werte:<br/>0 = Mahnung<br/>1 = Nachmahnung<br/>2 = Nachprüfung |
| Hauptfach              | I   | -     | V        | Verweis auf Tabelle **Faecher**<br/>Übergeordnetes Fach für das Feld „Fach“ |
| Bilingual              | A   | -     | V        | Verweis auf Tabelle **Kurssprachen**     |
| HausaufgabenVergessen  | S   | -     | -        | -                                        |
| ArbeitsmittelVergessen | S   | -     | -        | -                                        |
| Muendlich              | A   | 1     | -        | -                                        |
| Leistungsart           | A   | 20    | V        | Verweis auf Tabelle **Leistungarten**    |
| Bestanden              | A   | 1     | -        | Mögliche Werte:<br/>P = Bestanden<br/>F = Nicht bestanden<br/>N = Nicht belegt |
| Durchschnitt           | N   | -     | -        |                                          |
