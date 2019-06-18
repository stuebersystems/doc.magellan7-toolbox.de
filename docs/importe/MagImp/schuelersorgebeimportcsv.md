# Schnittstellenformat schueler_sorgebe.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname	|Typ	|Größe|	Bemerkung
--|--|--|--
SchuelerIDExtern	|I V P	||	Bitte derzeit nicht verwenden!
SchuelerVorname	|A V P|	30|	
SchuelerNachname	|A V P	|50|	
SchuelerGeburtsdatum	|D V P	|10|	In der Form TT.MM.JJJJ
SorgeIDExtern	|I V P	||	Bitte derzeit nicht verwenden!
SorgebeVorname|	A V P	|30|	
SorgebeNachname|	A V P	|50|	
SorgebeStrasse|	A V P	|100|	
SorgebeOrt	|A V P|	100|	
Verhaeltnis	|A P	|2	|Mögliche Werte:<br/>M = Mutter<br/>V = Vater<br/>E = Eltern<br/>EB = Erziehungsberechtigte(r)<br/>SB = Sorgeberechtigte(r)<br/>AP = Ansprechpartner(in)<br/>VM = Vormund<br/>GM = Großmutter<br/>GV = Großvater<br/>PF = Pflegeeltern<br/>EL = Eheleute
Benachrichtigung	|A|	2|	Mögliche Werte:<br/>I = Immer<br/>NF = Nur im Notfall<br/>N = Nie
TelefonPrioritaet	|A	|1	|Mögliche Werte:<br/>P = Telefon privat<br/>B = Telefon beruf<br/>M = Mobil
Position|	S	||	
Bemerkung	|M	|255	|


## Spaltenköpfe zur Vorlage für Importdateien



Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen. 


### Spaltenköpfe für schueler_sorge.import.csv, Stand: 30.06.2017



SchuelerIDExtern
SchuelerVorname
SchuelerNachname
SchuelerGeburtsdatum
SorgeIDExtern
SorgebeVorname
SorgebeNachname
SorgebeStrasse
SorgebeOrt
Verhaeltnis
Benachrichtigung
TelefonPrioritaet
Position
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




