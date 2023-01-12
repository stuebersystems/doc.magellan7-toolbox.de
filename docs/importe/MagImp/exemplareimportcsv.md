# Schnittstellenformat exemplare.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

!!! warning "Wichtig"

    Das Einlesen der Medienexemplare ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Medienexemplare.

Feld        | Anmerkung
----------- | ---------
**Feldname**| MediumTitel
Typ| A P
Größe| 100
Bemerkung| -
**Feldname**| Signatur
Typ| A P
Größe| 50
Bemerkung| -
**Feldname**| InventarNr
Typ| A
Größe| 15
Bemerkung| -
**Feldname**| Signaturnr
Typ| I
Größe| -
Bemerkung| -
**Feldname**| Zustand
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „MedienZustaende“ (Kuerzel)
**Feldname**| Eingangsdatum
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJ
**Feldname**| Betrag
Typ         | N
Größe       | -
Bemerkung   | -
**Feldname**| LieferantKuerzel
Typ| A V
Größe| 15
Bemerkung| Verweis auf die „Lieferanten“ (Kuerzel)
**Feldname**| Bemerkung
Typ| M
Größe| 255
Bemerkung| -

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für exemplare.import.csv, Stand: 23.02.2021

```
"MediumTitel";"Signatur";"InventarNr";"Signaturnr";"Zustand";"Eingangsdatum";"Betrag";"LieferantKuerzel";"Bemerkung"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld! 

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
