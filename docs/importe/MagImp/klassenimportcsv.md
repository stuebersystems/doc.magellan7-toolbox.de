# Schnittstellenformat klassen.import.csv

!!! warning "Wichtig"

    Das Einlesen der Klassen ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Daten und auch nicht zu doppelten Datensätzen.

## Zeitraumzuordnung der Klassen

### Beispiel für allgemeinbildende Klassen

Feld|Wert
---|---
ZeitraumVon:| 01.08.2012
ZeitraumBis:| 31.07.2013
Halbjahr:| 1
Ergebnis:| Die Klasse wird im 1. Halbjahr 2012/2013 angelegt.

!!! info "Hinweis"

    Möchten Sie, dass die Klasse in dem 1. und im 2. Halbjahr existiert (zwei Klassenzeiträume), benötigen Sie eine zweite Zeile in Ihrer Importdatei und tragen als Wert für das „Halbjahr“ eine „2“ ein. Ergebnis: Die Klasse wird im 1. und 2. Halbjahr 2012/2013 angelegt.

### Beispiel für berufsbildende Klassen

Um eine Klasse neu im 1. Halbjahr 2012/2013 anzulegen, erzeugen Sie eine Zeile mit folgenden Werten:

Feld|Wert
---|---
ZeitraumVon:| 01.08.2012
ZeitraumBis:  |31.07.2013
Halbjahr:| 1
Ergebnis: |Die Klasse wird im 1. Halbjahr 2012/2013 angelegt.

Startet die Klasse im 2. Halbjahr tragen Sie Folgendes ein:

Feld|Wert
---|---
ZeitraumVon:| 01.08.
ZeitraumBis: | 31.07.2013
Halbjahr:| 2

Möchten Sie für diese Klasse alle Klassenzeiträume vorab einrichten, ergeben sich für eine 3jährige Ausbildung insgesamt 6 Zeilen, die sich lediglich im Wert für das Halbjahr unterscheiden. Die Werte für „ZeitraumVon“ und „ZeitraumBis“ bilden die Gesamtdauer der Klasse ab.

Feld|Wert
---|---
ZeitraumVon:| 01.08.2012
ZeitraumBis: | 31.07.2015
Halbjahr: |1 (in weiteren Zeilen 2,3,4,5,6)
Ergebnis: |Die Klasse wird in 6 Halbjahren angelegt

!!! info "Hinweis"

    Pflichtfelder sind Kuerzel, Klassenart, Notenart, ZeitraumVon, ZeitraumBis und Halbjahr.
    Das Schuljahr muss für den Import (in der Importdatei und im Verzeichnis Zeiträume in MAGELLAN) im ersten Halbjahr am 01.08 starten und im zweiten Halbjahr mit dem 31.07. enden

## Importfelder

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feld|Anmerkung
---|---
**Feldname**| IDExtern
Typ| I
Größe| -
Bemerkung|  Bitte derzeit nicht verwenden!
**Feldname**| Kuerzel
Typ| A P
Größe| 15
Bemerkung| Klassenkürzel
**Feldname**| Klassenart
Typ| A P
Größe| 2
Bemerkung| Mögliche Werte:<br/>S = Standardklasse<br/>G = Ganztagsklasse<br/>KU = Oberstufenjahrgang (Nur Kurse)<br/>LG = Oberstufenjahrgang (Leistungs- und Grundkurse)<br/>A = Abschlussklasse<br/>K = Kombinationsklasse<br/>SK = Schulkindergarten
**Feldname**| Notenart
Typ|  A P
Größe| 1
Bemerkung| Mögliche Werte:<br/>N = Notenwerte<br/>P = Punktwerte<br/>B = Beurteilungen
**Feldname**| ZeitraumVon
Typ| D P
Größe| 10
Bemerkung|  In der Form TT.MM.JJJJ  Beginn der Gültigkeit der Klasse (01.08.JJJJ)
**Feldname**| ZeitraumBis
Typ| D P
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ  Ende der Gültigkeit der Klasse (31.07.JJJJ)
**Feldname**| Halbjahr
Typ| S P  
Größe| -
Bemerkung| Mögliche Werte: 1 2
**Feldname**| KuerzelAlpha
Typ| A
Größe| 8
Bemerkung|
**Feldname**| Kuerzelstatistik
Typ| A
Größe| 20
Bemerkung| Klassenkürzel für die Statistik
**Feldname**| Langname1
Typ| A
Größe| 100
Bemerkung| -
**Feldname**| Langname2
Typ| A
Größe| 100
Bemerkung| -
**Feldname**| Abteilung
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Abteilungen“ (Kuerzel)
**Feldname**| Schulform
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Schulformen“ (Kuerzel)
**Feldname**| Schulart
Typ| A V
Größe|  20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Schularten“ (Kuerzel)
**Feldname**| Organisation
Typ| A V
Größe| 20
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Organisationen“ (Kuerzel)
**Feldname**| Behinderung
Typ| A V
Größe|  20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Behinderungsarten“ (Kuerzel)
**Feldname**| Beruf
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Berufe“ (Kuerzel)
**Feldname**| Bildungsgang
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
**Feldname**| Integration
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Integrationsmerkmale“ (Kuerzel)
**Feldname**| Berufsfeld
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Berufsfelder“ (Kuerzel)
**Feldname**| Einzelintegration
Typ| L
Größe| -
Bemerkung| -
**Feldname**| Laenderuebergreifend
Typ| L
Größe| -
Bemerkung| -
**Feldname**| Regelbetrag
Typ| N
Größe| -
Bemerkung| -
**Feldname**| Schulartuebergreifend
Typ| L  
Größe| -
Bemerkung| -
**Feldname**| Schulstelle
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Schulstellen“ (Kuerzel)
**Feldname**| Bemerkung
Typ| M
Größe|  255
Bemerkung| -
**Feldname**| Foerderung
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Foerderungen“ (Kuerzel)
**Feldname**| Klassenleiter1IDExtern
Typ| I V
Größe| -
Bemerkung|  Bitte derzeit nicht verwenden!
**Feldname**| Klassenleiter1Kuerzel
Typ| A V
Größe| 6
Bemerkung| Verweis auf „Lehrer“ (Kuerzel)
**Feldname**| Klassenleiter2IDExtern
Typ| I V
Größe| -
Bemerkung|  Bitte derzeit nicht verwenden!
**Feldname**| Klassenleiter2Kuerzel
Typ| A V
Größe| 6
Bemerkung| Verweis auf „Lehrer“ (Kuerzel)
**Feldname**| Jahrgang
Typ| S  
Größe| -
Bemerkung| -
**Feldname**| Klassenstufe
Typ| A V
Größe|  10
Bemerkung|  Verweis auf das Schlüsselverzeichnis „Klassenstufen“ (Kuerzel)
**Feldname**| MerkmalA1<br/>MerkmalA2<br/>MerkmalA3<br/>MerkmalA4<br/>MerkmalA5<br/>MerkmalA6
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „KlassenMerkmale“ (Kuerzel) <br/>Freies Merkmal
**Feldname**| MerkmalB1<br/>MerkmalB2<br/>MerkmalB3<br/>MerkmalB4
Typ| A
Größe| 1
Bemerkung| -
**Feldname**| MerkmalS1<br/>MerkmalS2<br/>MerkmalS3<br/>  MerkmalS4
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „KlassenMerkmale“ (Kuerzel)  Statistikmerkmal

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für klassen.import.csv, Stand: 23.02.2021

 ```
"Kuerzel";"Klassenart";"Notenart";"ZeitraumVon";"ZeitraumBis";"Halbjahr";"KuerzelAlpha";"Kuerzelstatistik";"Langname1";"Langname2";"Abteilung";"Schulform";"Schulart";"Organisation";"Behinderung";"Beruf";"Bildungsgang";"Integration";"Berufsfeld";"Einzelintegration";"Laenderuebergreifend";"Regelbetrag";"Schulartuebergreifend";"Schulstelle";"Bemerkung";"Foerderung";"Klassenleiter1Kuerzel";"Klassenleiter2Kuerzel";"Jahrgang";"Klassenstufe";"MerkmalA1";"MerkmalA2";"MerkmalA3";"MerkmalA4";"MerkmalA5";"MerkmalA6";"MerkmalB1";"MerkmalB2";"MerkmalB3";"MerkmalB4";"MerkmalS1";"MerkmalS2";"MerkmalS3";"MerkmalS4" 
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
