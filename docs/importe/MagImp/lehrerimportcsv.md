# Schnittstellenformat lehrer.import.csv

Die Datei lehrer.import.csv dient dem Import der Lehrer-Stammdaten. Grundsätzlich wird, wie in allen anderen Importdateien jeder Schüler einmalig in Magellan hinzugefügt, übereinstimmende Lehrer (Kürzel) werden übersprungen.
Eine Ausnahme stellt der Import der Lehrer-Stammdaten dar, bei dem eine Aktualisierung unter vorgegebenen Bedingungen möglich ist.

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname| Typ| Größe| Bemerkung
--|--|--|--
Kuerzel |A P |6| Lehrerkürzel
Vorname| A| 100| -
Nachname |A| 100| -
Anrede| A |3 |Mögliche Werte:<br/><br/>F = Frau<br/>H = Herr<br/>FD= Frau Dr.<br/>HD = Herr Dr.<br/>FP = Frau Prof.<br/>HP = Herr Prof.<br/>FPD = Frau Prof. Dr.<br/>HPD = Herr Prof. Dr.<br/>MS = Ms.<br/>MRS = Mrs.<br/>MR = Mr.
Geschlecht| A |1| Mögliche Werte:<br/>W = weiblich<br/>M = männlich
Geburtsdatum |D |10| In der Form TT.MM.JJJJ
Geburtsort |A| 100 |-
Geburtsname |A |50|-
Ehestand |A| 1 |Mögliche Werte:<br/>V = verheiratet<br/>N = nicht verheiratet<br/>L = ledig<br/>G = geschieden<br/>W = verwitwet
Strasse| A| 100|
Land |A |3 |Landeskennzeichen z.B. „D“, „CH“
PLZ| A| 5| Postleitzahl
Ort |A |100| -
Ortsteil|||  -
Gemeinde |A V |8| Verweis auf das Schlüsselverzeichnis „Gemeinden“ (Postleitzahlen)
Telefon| A |30| -
Telefax| A |30 |-
Mobil |A |30 |-
Email |A |100 |-
TelefonDienst |A| 30 |-
TelefaxDienst| A |30| -
KFZ1| A| 15 |KFZ-Kennzeichen 1
KFZ2| A| 15 |KFZ-Kennzeichen 2
Kategorie |A V| 20| Verweis auf das Schlüsselverzeichnis „Lehrerkategorien“ (Kuerzel)
Staatsangeh |A V |20| Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“ (Kuerzel)
Konfession |A V| 20 |Verweis auf das Schlüsselverzeichnis „Konfessionen“ (Kuerzel)
Bevollmaechtigung| A V| 20| Verweis auf das Schlüsselverzeichnis „Bevollmaechtigungen“ (Kuerzel)
Personalnr |A |15 |Personalnummer
Statistiknr| A |15 |Statistiknummer
ZugangDatum |D |20 |Zugangsdatum in der Form TT.MM.JJJJ
ZugangGrund |A V |20| Verweis auf das Schlüsselverzeichnis „LehrerZugaenge“ (Kuerzel)
AbgangDatum |D |10| Abgangsdatum in der Form TT.MM.JJJJ
AbgangGrund |A V |10| Verweis auf das Schlüsselverzeichnis „LehrerAbgaenge“ (Kuerzel)
Amtsbez| A V |20| Verweis auf das Schlüsselverzeichnis „Amtsbez“ (Kuerzel)
Dienstbez| A V |20 |Verweis auf das Schlüsselverzeichnis „Dienstbez“ (Kuerzel)
Dienstverh |A V |20 |Verweis auf das Schlüsselverzeichnis „Dienstverh“ (Kuerzel)
Beschaeftigungsverh |A V |20 |Verweis auf das Schlüsselverzeichnis „Beschaeftigungsverh“ (Kuerzel)
MerkmalA1,<br/>MerkmalA2,<br/>MerkmalA3,<br/>MerkmalA4,<br/>MerkmalA5,<br/>MerkmalA6 |A V |20| Verweis auf das Schlüsselverzeichnis „LehrerMerkmale“ (Kuerzel), <br/>Freies Merkmal
MerkmalB1| A| 15| -
MerkmalB2| A| 15| -
MerkmalB3| A| 15| -
MerkmalB4| A| |15| -
MerkmalS1,<br/>MerkmalS2,<br/>MerkmalS3,<br/>MerkmalS4| A V |20 |Verweis auf das Schlüsselverzeichnis LehrerMerkmale“ (Kuerzel)<br/>Statistikmerkmal
Status| A |1| Mögliche Werte:<br/>N = inaktiv<br/>J = aktiv
Bemerkung |M| 255 |-

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für lehrer.import.csv, Stand: 23.02.2021

```
"Kuerzel";"Vorname";"Nachname";"Anrede";"Geschlecht";"Geburtsdatum";"Geburtsort";"Geburtsname";"Ehestand";"Strasse";"Land";"PLZ";"Ort";"Ortsteil";"Gemeinde";"Telefon";"Telefax";"Mobil";"Email";"TelefonDienst";"TelefaxDienst";"KFZ1";"KFZ2";"Kategorie";"Staatsangeh";"Konfession";"Bevollmaechtigung";"Personalnr";"Statistiknr";"ZugangDatum";"ZugangGrund";"AbgangDatum";"AbgangGrund";"Amtsbez";"Dienstbez";"Dienstverh";"Beschaeftigungsverh";"MerkmalA1";"MerkmalA2";"MerkmalA3";"MerkmalA4";"MerkmalA5";"MerkmalA6";"MerkmalB1";"MerkmalB2";"MerkmalB3";"MerkmalB4";"MerkmalS1";"MerkmalS2";"MerkmalS3";"MerkmalS4";"Status";"Bemerkung"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon``aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
