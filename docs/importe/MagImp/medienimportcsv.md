# Schnittstellenformat medien.import.csv


Die Importdatei kann maximal aus folgenden Feldern bestehen:


Feld|Anmerkung
---|---
**Feldname**|	IDExtern 
Typ|	 I P 
Größe|	- 
Bemerkung|	 Bitte derzeit nicht verwenden 
**Feldname**|	Titel 
Typ|	 A P 
Größe|	100
Bemerkung|	 - 
**Feldname**|	Mehrjahresband 
Typ|	 L P 
Größe|	- 
Bemerkung|	Mögliche Werte:<br/>J = Mehrjahresband (beim Import vorgegeben)<br/>N = Kein Mehrjahresband
**Feldname**|	Status 
Typ|	 A P 
Größe|	1
Bemerkung|	 Mögliche Werte:<br/>J = ausleihbar (beim Import vorgegeben)<br/>N = nicht ausleihbar
**Feldname**|	Untertitel 
Typ|	 A 
Größe|	100
Bemerkung|	 - 
**Feldname**|	Barcode 
Typ|	 A 
Größe|	20
Bemerkung|	 - 
**Feldname**|	Medienart 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Medienarten“ (Kuerzel) 
**Feldname**|	Medienkategorie 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Medienkategorien“ (Kuerzel) 
**Feldname**|	Standort 
Typ|	 A V 
Größe|	10
Bemerkung|	Verweis auf das Schlüsselverzeichnis „Standorte“ (Kuerzel)
**Feldname**|	VerlagIDExtern 
Typ|	 I V 
Größe|	- 
Bemerkung|	Bitte derzeit nicht verwenden! 
**Feldname**|	VerlagKuerzel 
Typ|	 A V 
Größe|	15
Bemerkung|	 Verweis auf die „Verlage“ (Kuerzel 
**Feldname**|	Herausgeber 
Typ|	 A 
Größe|	50
Bemerkung|	 - 
**Feldname**|	Autor 
Typ|	 A 
Größe|	50
Bemerkung|	 - 
**Feldname**|	Signaturvorgabe 
Typ|	 A 
Größe|	50
Bemerkung|	 - 
**Feldname**|	Copyright 
Typ|	 A 
Größe|	50
Bemerkung|	 - 
**Feldname**|	ISBN 
Typ|	 A 
Größe|	20
Bemerkung|	 - 
**Feldname**|	ISSN 
Typ|	 A 
Größe|	20
Bemerkung|	 - 
**Feldname**|	Erscheinungsjahr 
Typ|	 S 
Größe|	4
Bemerkung|	In der Form JJJJ 
**Feldname**|	Erscheinungsland 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Staaten“ (Kuerzel) 
**Feldname**|	Erscheinungsweise 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Erscheinungsweisen“ (Kuerzel) 
**Feldname**|	Sprache 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Sprachen“ (Kuerzel) 
**Feldname**|	Format 
Typ|	 A V 
Größe|	10
Bemerkung|	 Verweis auf das Schlüsselverzeichnis „Medienformate“ (Kuerzel) 
**Feldname**|	Umfang 
Typ|	 S 
Größe|	 - 
Bemerkung|	Z.B. Anzahl der Seiten 
**Feldname**|	Serie 
Typ|	C 
Größe|	30
Bemerkung|	 - 
**Feldname**|	Band 
Typ|	 A 
Größe|	30
Bemerkung|	 - 
**Feldname**|	Heft 
Typ|	 A 
Größe|	30
Bemerkung|	 - 
**Feldname**|	Ausgabe 
Typ|	 A 
Größe|	30
Bemerkung|	 - 
**Feldname**|	Jahrgang 
Typ|	 S 
Größe|	- 
Bemerkung|	 Jahrgangsstufe 
**Feldname**|	Zusammenfassung 
Typ|	 M 
Größe|	255
Bemerkung|	 - 
**Feldname**|	Bemerkung 
Typ|	 M 
Größe|	255
Bemerkung|	 - 


    
> #### warning::Wichtig!
>
> Importierte Medien aus der Datei „medien.import.csv“ können erst in der MAGELLAN-Bibliothek angezeigt werden, wenn die dazugehörige Datei „exemplare.import.csv“ importiert wurde.
Das Einlesen der Medien ist nur für den einmaligen Import gedacht. Ein erneutes Einlesen der gleichen Daten führt nicht zu einem Update der bereits eingelesenen Mediendaten


## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.




### Spaltenköpfe für medien.import.csv, Stand: 30.06.2017






IDExtern 
Titel 
Mehrjahresband 
Status 
Untertitel 
Barcode 
Medienart 
Medienkategorie 
Standort 
VerlagIDExtern 
VerlagKuerzel 
Herausgeber 
Autor 
Signaturvorgabe 
Copyright 
ISBN 
ISSN 
Erscheinungsjahr 
Erscheinungsland 
Erscheinungsweise 
Sprache 
Format 
Umfang 
Serie 
Band 
Heft 
Ausgabe 
Jahrgang 
Zusammenfassung 
Bemerkung 

> #### warning::Wichtig!
>
> Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld! 






### Das Ergebnis wird als senkrechte Spalte angezeigt?

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt?

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt ` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen ``aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)



