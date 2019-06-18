# Schnittstellenformat schueler_ausbildung.import.csv

## Bewerber oder Schüler
Wenn zuvor Schüler mit dem Status "SB" importiert wurden und ein Schüler evtl. zweimal, einmals als
Schüler und einmal als Bewerber, in Magellan vorhanden ist, dann prüft der Import zuvor, 
ob ein Schüler mehrfach existiert und aktualisiert die Ausbildung für den Schüler mit dem
gefüllten Feld "IDIntern".

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname|	Typ|	Größe|	Bemerkung
--|--|--|--
SchuelerIDExtern	|I V P	||	Bitte derzeit nicht verwenden!
SchuelerVorname	|A V P	|30|	-
SchuelerNachname	|A V P	|50|	-
SchuelerGeburtsdatum	|D V P	|10|	In der Form TT.MM.JJJJ
BetriebIDExtern	|I V P	||	Bitte derzeit nicht verwenden!
BetriebKuerzel	|A V P	|10	|Verweis auf „Betriebe“ (Kuerzel)
Beruf	|A V	|10|	Verweis auf das Schlüsselverzeichnis „Berufe“ (Kuerzel)
Bildungsgang|	A V	|10|	Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
AusbildungVon	|D	|10	|Beginn der Ausbildung <br/>In der Form TT.MM.JJJJ
AusbildungBis	|D|	10|	Ende der Ausbildung<br/>In der Form TT.MM.JJJJ
Ausbildungsdauer|	N||		-
Vertrag	|L		||Ausbildungsvertrag
Vertragsart|	A V	|10|	Verweis auf das Schlüsselverzeichnis „Vertragsarten“ (Kuerzel)
Vertragsnr	|A	|10	|Vertragsnummer
VertragVorgelegtAm|	D	|10|	In der Form TT.MM.JJJJ
Bemerkung	|M|	255	|-
AusbilderKontaktIDExtern	|I V||		Bitte derzeit nicht verwenden!
AusbilderKontaktNachname	|A V	|50|	-
AusbilderKontaktVorname	|A V|	30|	
AusbilderKontaktGeschlecht	|A V	|1|	Mögliche Werte:<br/>W = weiblich<br/>M = männlich
AusbilderKontaktTelefon|A|30|
AusbilderKontaktMobil|A|30|
AusbilderKontaktEmail|A|100|
PraxisBetriebIDExtern	|I V	||	Bitte derzeit nicht verwenden!
PraxisBetriebKuerzel	|A V	|10	|Verweis auf „Betriebe“ (Kuerzel)
PraxisVon	|D|	10|In der Form TT.MM.JJJJ
PraxisBis	|D	|10	|In der Form TT.MM.JJJJ
Praxisdauer|	N||		
PraxisKontaktIDExtern	|I V	||	Bitte derzeit nicht verwenden!
PraxisKontaktNachname|	A V	|50|-	
PraxisKontaktVorname|	A V	|30|-	
PraxisKontaktGeschlecht	|A V|	1	|Mögliche Werte:<br/>W = weiblich<br/>M = männlich
PraxisKontaktTelefon|A|30|
PraxisKontaktMobil|A|30|
PraxisKontaktEmail|A|100|


## Spaltenköpfe zur Vorlage für Importdateien



Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen. 

### Spaltenköpfe für schueler_ausbildung.import.csv, Stand: 30.06.2017




SchuelerIDExtern 
SchuelerVorname 
SchuelerNachname 
SchuelerGeburtsdatum 
BetriebIDExtern 
BetriebKuerzel 
Beruf 
Bildungsgang
AusbildungVon 
AusbildungBis 
Ausbildungsdauer
Vertrag 
Vertragsart
Vertragsnr 
VertragVorgelegtAm
Bemerkung 
AusbilderKontaktIDExtern 
AusbilderKontaktNachname 
AusbilderKontaktVorname 
AusbilderKontaktGeschlecht 
AusbilderKontaktTelefon
AusbilderKontaktMobil
AusbilderKontaktEmail
PraxisBetriebIDExtern 
PraxisBetriebKuerzel 
PraxisVon 
PraxisBis 
Praxisdauer
PraxisKontaktIDExtern 
PraxisKontaktNachname
PraxisKontaktVorname
PraxisKontaktGeschlecht 
PraxisKontaktTelefon
PraxisKontaktMobil
PraxisKontaktEmail

> #### warning::Wichtig!
>
> Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!





### Das Ergebnis wird als senkrechte Spalte angezeigt?

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt?

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt ` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen ``aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)



