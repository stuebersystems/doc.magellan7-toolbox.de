# Schnittstellenformat schulen.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feld|Anmerkung
---|---
**Feldname**|  IDExtern
Typ|  I P
Größe| -
Bemerkung|  Bitte derzeit nicht verwenden
**Feldname**|  Kuerzel
Typ|  AP
Größe| 15
Bemerkung|  Kürzel der Schule
**Feldname**|  Name1
Typ|  A
Größe| 50
Bemerkung|  -
**Feldname**|  Name2
Typ|  A
Größe| 50
Bemerkung|  -
**Feldname**|  Strasse
Typ|  A
Größe| 100
Bemerkung|  -
**Feldname**|  Land
Typ|  A
Größe| 3
Bemerkung|  Landeskennzeichen z.B. „D“, „CH“
**Feldname**|  PLZ
Typ|  A
Größe| 5
Bemerkung|  Postleitzahl
**Feldname**|  Ort
Typ|  A
Größe| 100
Bemerkung|  -
**Feldname**|  Ortsteil
Typ|  A
Größe| 100
Bemerkung|  -
**Feldname**|  Gemeinde
Typ|  A V
Größe| 8
Bemerkung| Verweis auf das Schlüsselverzeichnis „Gemeinden“ (Postleitzahlen)
**Feldname**|  Telefon
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Telefax
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Email
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  Internet
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  Schulform
Typ|  A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Schulformen“
**Feldname**| Schulnummer
Typ|  A
Größe| 8
Bemerkung| -
**Feldname**| Bemerkung
Typ|  M
Größe| 255
Bemerkung| -
**Feldname**|  Status
Typ|  A
Größe| 1
Bemerkung| Mögliche Werte:<br/>N = inaktiv<br/>J = aktiv

!!! warning "Wichtig"

    Das Einlesen der Schulen ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Daten und auch nicht zu doppelten Datensätzen. Die Datensätze werden anhand des Kürzels identifiziert.

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schulen.import.csv, Stand: 23.02.2021

```
"Kuerzel";"Name1";"Name2";"Strasse";"Land";"PLZ";"ort";"Ortsteil";"Gemeinde";"Telefon";"Telefax";"Email";"Internet";"Schulform";"Schulnummer";"Status"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt?

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
