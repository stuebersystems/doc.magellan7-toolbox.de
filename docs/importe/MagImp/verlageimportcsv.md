# Schnittstellenformat verlage.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feld|Anmerkung
---|---
**Feldname**|  Kuerzel
Typ|  A P
Größe| 15
Bemerkung|  Verlagskürzel
**Feldname**|  Name1
Typ|  A
Größe| 50
Bemerkung| -
**Feldname**|  Name2
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Strasse
Typ|  A
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
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  Ortsteil
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**|  Telefon
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Telefax
Typ|  A
Größe| 30
Bemerkung| -
**Feldname**|  Internet
Typ|  A
Größe| 100
Bemerkung| -
**Feldname**| Bemerkung
Typ|  M
Größe| 255
Bemerkung| -

!!! warning "Wichtig"

    Das Einlesen der Verlage ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Daten und  auch nicht zu doppelten Datensätzen. Die Datensätze werden anhand des Feldes **Kuerzel** identifiziert.

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für verlage.import.csv, Stand: 23.02.2021

```
"Kuerzel";"Name1";"Name2";"Strasse";"Land";"PLZ";"Ort";"Ortsteil";"Telefon";"Telefax";"Internet";"Bemerkung"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld! 

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
