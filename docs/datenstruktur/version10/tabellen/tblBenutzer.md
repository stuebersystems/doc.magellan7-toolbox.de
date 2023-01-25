
# Tabelle Benutzer


Feldname               | Typ | Größe | Funktion | Bemerkung
---------------------- | --- | ----- | -------- | ---------
Mandant                | I   | -     | PV       | Verweis auf Tabelle **Mandanten**
ID                     | I+  | -     | P        | -
Nachname               | A   | -     | -        | -
Vorname                | A   | -     | -        | -
Kennung                | A   | -     | -        | -
Lehrer                 | I   | -     | -        | Verweis auf Tabelle **Lehrer**
Email                  | A   | 100   | -        |
Gruppe1                | S   | -     | -        | Rechte für `Schulverwaltung`:<br/>0=Schulleitung1<br/>1=Sekretatiat1<br/>2=Kollegium1<br/>3=Gast1<br/>4=Schulleitung2<br/>5=Sekretariat2<br/>6=Kollegium2<br/>7=Kollegium3<br/>8=Kollegium4<br/>9=Gast2<br/>10=Statistikadmin
Gruppe2                | S   | -     | -        |für `Medienverwaltung`:<br/>0=Schulleitung<br/>1=Bibliothekar<br/>2=Kollegium<br/>3=Gast
Gruppe3                | S   | -     | -        | ehemals `Haushalt & Inventar`
Gruppe4                | S   | -     | -        | ehemals `Klassenbuch`
Gruppe5                | S   | -     | -        | ehemals `DatawareHouse`
AdminMandant           | S   | -     | -        | -
MedienKatalog          | I   | -     | -        | Verweis auf Tabelle **MedienKataloge**
StatusVerzeichnisse    | S   | -     | -        | -
StatusImportExport     | S   | -     | -        | -
StatusDrucken          | S   | -     | -        | -
StatusDokumente        | S   | -     | -        | -
StatusBerufsschule     | S   | -     | -        | -
StatusBBSPruefungsnote | S   | -     | -        | -
Status                 | S   | -     | -        | Teilnahme in MyMAGELLAN. Mögliche Werte:<br>0 = (Kein Teilnehmer)<br>1 = Teilnehmer
LetzterExport_Datum    | D   | -     | -        | -
LetzterExport_Uhrzeit  | T   | -     | -        | -
LetzterImport_Datum    | D   | -     | -        | -
LetzterImport_Uhrzeit  | T   | -     | -        | -
DatenVerz              | A   | 100   | -        | -
MyMagellanKennwort     | A   | 32    | -        | -
Aktiv                  | S   | -     | -        | Mögliche Werte:<br>0 = Inaktiv<br>1 = Aktiv

