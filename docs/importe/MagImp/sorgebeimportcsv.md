# Schnittstellenformat sorgebe.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen: 

Feld|Anmerkung
---|---
**Feldname**|  IDExtern
Typ|  I P
Größe| -
Bemerkung|  Bitte derzeit nicht verwenden
**Feldname**|  Vorname
Typ|  A P
Größe| 100
Bemerkung| -
**Feldname**|  Nachname
Typ|  A P
Bemerkung| -
Größe| 100
**Feldname**|  Anrede
Typ|  A
Größe| 3
Bemerkung| Mögliche Werte:<br/>F = Frau<br/>H = Herr<br/>FD= Frau Dr.<br/>HD = Herr Dr.<br/>FP = Frau Prof.<br/>HP = Herr Prof.<br/>FPD = Frau Prof. Dr.<br/>HPD = Herr Prof. Dr.<br/>FA = Familie<br/>HF = Herr und Frau<br/>MS = Ms.<br/>MRS = Mrs.<br/>MR = Mr.<br/>MRMS = Mr. and Ms.<br/>MRMRS = Mr. and Mrs.<br/>EH = Eheleute
**Feldname**|  Strasse
Typ|  P2
Größe| 100
Bemerkung| -
**Feldname**|  Land
Typ|  A
Größe| 3
Bemerkung|  Landeskennzeichen z.B. „D“, „CH“
**Feldname**|  PLZ
Typ|  A
Größe| 5
Bemerkung| Postleitzahl
**Feldname**|  Ort
Typ|  A P2
Größe| 100
Bemerkung| -
**Feldname**|  Ortsteil
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  TelefonPrivat
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  TelefonBeruf
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Mobil
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Email
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  Beruf
Typ|  A
Größe| 50
Bemerkung| -
**Feldname**|  Geburtsland
Typ|  A V
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“
**Feldname**|  Staatsangeh1
Typ|  A V
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“
**Feldname**|  Staatsangeh2
Typ|  A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“
**Feldname**|  Muttersprache
Typ|  A V
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Muttersprachen“
**Feldname**|  Verkehrssprache
Typ|  A V
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Muttersprachen“
**Feldname**|  Funktion1 –<br/>Funktion8
Typ|  A
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „SorgebeFunktionen"
**Feldname**|  Status2
Typ|  A
Größe| 1
Bemerkung| Gibt an, ob der Sorgeberechtigte aktiv oder inaktiv ist.<br/>Mögliche Werte:<br/>N = inaktiv<br/>J = aktiv
**Feldname**| Bemerkung
Typ|  M
Größe| 255
Bemerkung| -

!!! warning "Wichtig"

    Das Einlesen der Sorgeberechtigten ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Daten und auch nicht zu doppelten Datensätzen. Die Datensätze werden anhand des Vor- und Nachnamens identifiziert.

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für sorgebe.import.csv, Stand: 23.02.2021

```
"Vorname";"Nachname";"Anrede";"Strasse";"Land";"PLZ";"Ort";"Ortsteil";"TelefonPrivat";"TelefonBeruf";"Mobil";"Email";"Beruf";"Geburtsland";"Staatsangeh1";"Staatsangeh2";"Muttersprache";"Verkehrssprache";"Funktion1";"Funktion2";"Funktion3";"Funktion4";"";"unktion5";"Funktion6";"Funktion7";"Funktion8";"Status2";"Bemerkung"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
