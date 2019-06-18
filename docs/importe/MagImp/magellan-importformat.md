# MAGELLAN-Importformat {#Magellan-Importformat}

Das MAGELLAN-Importformat ermöglicht den Import von Daten aus Textdateien nach Magellan. Diese Textdateien müssen dazu dem im Folgenden beschriebenen Format entsprechen. Der eigentliche Import erfolgt mit Hilfe des Magellan-Administrators. 

## Übersicht der Importdateien
Jede Datei muss wie in der Spalte „Importdatei“ der folgenden Auflistung benannt sein. Die Dateien sind in der empfohlenen Importreihenfolge aufgelistet. Die Importreihenfolge ist wichtig für die Dateien, die auf zuvor importierte Daten zurückgreifen müssen. 

**Beispiel:** 

Die Datei „schueler_sorgebe.import.csv“ kann nur sinnvoll importiert werden, wenn zuvor die Dateien „sorgebe.import.csv“ und „schueler.import.csv“ importiert wurden. 

Importdatei|Beschreibung
---|---
[schulen.import.csv](schnittstellenformat_schulenimportcsv.md)|Enthält die Stammdaten der Schulen
[betriebe.import.csv](betriebeimportcsv.md)|Enthält die Stammdaten der Betriebe
[lehrer.import.csv](lehrerimportcsv.md)|Enthält die Stammdaten der Lehrer
[schueler.import.csv](lehrerimportcsv.md)|Enthält die Stammdaten der Schüler und Bewerber
[sorgebe.import.csv](sorgebeimportcsv.md)|Enthält die Stammdaten der Sorgeberechtigten
[verlage.import.csv](verlageimportcsv.md)|Enthält die Stammdaten der Verlage
[lieferanten.import.csv](lieferantenimportcsv.md)|Enthält die Stammdaten der Lieferanten
[medien.import.csv](lieferantenimportcsv.md)|Enthält die Stammdaten der Medien

Alle nachfolgenden Dateien verbinden vorab importierte Daten miteinander:

Importdatei|Beschreibung
---|---
[exemplare.import.csv](exemplareimportcsv.md)|Enthält die Exemplardaten zu den Medien<br/>Bedingung:<br/> Import der medien.import.csv
[klassen.import.csv](klassenimportcsv.md)	|Enthält die Stamm- und Zeitraumdaten der Klassen<br/>Bedingung: <br/>Vorhandensein der Zeiträume und Lehrer (Verweis auf Klassenleiter) in MAGELLAN.
[schueler_laufbahn.import.csv](schuelerlaufbahn_importcsv.md) |Enthält die Laufbahndaten der Schüler <br/>Weitere Bedingung: <br/>Import der klassen.import.csv und schueler.import.csv
[schueler_fachdaten.import.csv](schuelerfachdatenimportcsv.md) |	Enthält die Fachdaten der Schüler<br/>Weitere Bedingung:<br/> Import der klassen.import.csv, schueler.import.csv und schueler_laufbahn.import.csv
[schueler_sorgebe.import.csv](schuelersorgebeimportcsv.md)|Enthält die Zuordnung der Sorgeberechtigten zu den Schülern<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und sorgebe.import.csv
[schueler_schulen.import.csv](schuelerschulenimportcsv.md)|	Enthält die bereits besuchten Schulen der Schüler (Stichwort: Herkunftsschulen)<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und schulen.import.csv
[schueler_ausbildung.import.csv](schuelerausbildungimportcsv.md)|Enthält die Ausbildungsdaten der Schüler<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und betriebe.import.csv

> #### warning::Wichtig!
>
> 	Reihenfolge des Einlesens: 
>	Da die Importdateien teilweise aufeinander aufbauende Daten enthalten, empfehlen wir die obenstehende Reihenfolge beim Import einzuhalten.
									

## Aufbau der Importdateien

Jede dieser Dateien muss als CSV-Datei aufgebaut sein, d.h. sie besteht jeweils aus einer Kopfzeile und ein oder mehreren Zeilen mit den zu importierenden Inhalten. Die einzelnen Felder sind durch Semikolon getrennt und mit Anführungszeichen abgegrenzt.

Die Schülerdatei kann z.B. folgenden Aufbau haben
„Nachname“;„Vorname“;„Anrede“;„Geschlecht“;„Strasse“;
* <FONT FACE="Courier New">„Müller“;„Hans“;„H“;„m“;„Mühlenweg 11“
* <FONT FACE="Courier New">„Meier“;„Petra“;„F“;„w“;„Mühlenweg 12“</FONT>

Die Reihenfolge der Felder spielt dabei keine Rolle. Die Semantik der Felder wird durch die Kopfzeile bestimmt. Beispielsweise kann auch eine Schülerdatei mit folgendem Aufbau eingelesen werden.
„Strasse“;„Geschlecht“;„Vorname“;„Nachname“;„Anrede“
* <FONT FACE="Courier New">„Mühlenweg 11“;„m“;„Müller“;„Hans“;„H“
* <FONT FACE="Courier New">„Mühlenweg 12“;„w“;„Meier“;„Petra“;„F“</FONT>

Die Felder entsprechen dem sog. System Data Format (SDF), d.h. bei einem Semikolon, Komma, Sonderzeichen oder einem Leerzeichen im String wird der String in Anführungszeichen gesetzt, z.B. die Strasse "Mühlenweg 11" wird
* <FONT FACE="Courier New">;“Mühlenweg 11“;...</FONT>
und nicht
* <FONT FACE="Courier New">;Mühlenweg 11;...</FONT>

geschrieben.

Besitzt der Inhalt selbst Anführungszeichen, so sind doppelte Anführungszeichen anzugeben. Wollen Sie z.B. “Hallbach“ einlesen, so müssen Sie als Inhalt
* <FONT FACE="Courier New">;““Hallbach““;...</FONT>

angeben.
Welche Felder pro Datei eingelesen werden, ist den nachfolgenden Abschnitten pro Datei zu entnehmen.

> Zeilenumbrüche sind in einer CSV-Datei nicht erlaubt. Das Datenformat bestimmt jede Zeile als einen Datensatz. Ein Umbruch mitten in der Zeile kann nicht verarbeitet werden. Wir erlauben in den Feldern, die mit dem Datentyp M für Memofeld gekennzeichnet sind Zeilenumbrüche in Form der Notation: \n. Beim Import wird diese Notation in einen echten Zeilenumbruch umgewandelt.

## Datentypen
Bei der Beschreibung finden folgende Datentypen Verwendung

Typ|Beschreibung
---|---
A|Textfeld mit maximaler Länge (Textfeld)
D |Datumsangabe , Format: TT.MM.JJJJ (Datumsfeld) </td>
I |Ganze Zahl (32-Bit-Integer 
L |Logisches Feld: Textfeld der Größe 1 mit den möglichen Werten "J" oder "N" 
M |Textfeld mit variabler Länge (Memofeld)
N |Kommazahl (Numeric) z.B. „2,5“ oder „2.5“	</td>
S |Ganze Zahl (16-Bit-Integer)

Einige Felder haben auch eine bestimmte Funktion in der Datei und werden als Zusatz zum Typ dargestellt. Diese Funktion wird ebenfalls durch ein zusätzliches Kürzel gekennzeichnet.

Typ|Beschreibung
---|---
P|Pflichtfeld. Es muss mindestens pro Datensatz gefüllt sein, damit der Datensatz importiert werden kann. </td>
P2 |Sekundärpflichtfelder. Diese sind für den Import insoweit relevant, dass wir Felder mit P und P2 berücksichtigen, wenn wir überprüfen, ob ein Datensatz bereits existiert. Für den Import selbst, sind Eingaben in P2 Felder dann nicht relevant. Relevant wird es, wenn Verweise auf Tabellen mit P2 Feldern existieren. Denn dann kann ein Import dieser Verweise nur gewährleistet werden, wenn P1 und P2 Felder übereinstimmen.
V |Verweis. Gibt an, dass der eigentliche Stammsatz in einer anderen Tabelle liegt und hier nur der Verweis darauf gespeichert ist. Dies kann eine Zahl (ID) sein, oder ein Textkürzel. </td>

> #### danger::Achtung!
>
> Pflichtfelder müssen angegeben werden, andere Felder können angegeben werden. Die Kombination der Inhalte der Pflichtfelder einer Datei muss eindeutig sein. Ist keine oder nur eine Untermenge der Pflichtfelder angegeben, erfolgt kein Import.

Wenn Sie eines der Pflichtfelder einer Datei in Ihrem Dateiformat noch nicht besitzen, so müssen Sie diese zusätzlich vor dem Import anlegen und mit entsprechenden Werten füllen. Dabei müssen Sie immer die Eindeutigkeit der Kombination der Inhalte der Pflichtfelder berücksichtigen.
Bei den Textfeldern ist zusätzlich auch eine Größe angegeben, die der maximalen Größe der Felder in Magellan entspricht. Bei der Größe handelt es sich um die Anzahl der Zeichen pro Feld. Haben die einzulesenden Inhalte einen größeren Wert, so werden die Felder beim Import übersprungen und Sie erhalten für diese Datensätze eine entsprechende Meldung.

**Beispiel**:
Die Schulnummer ist in der Datei schulen.import.csv wie folgt definiert:

Feld|Wert
---|---
Feldname| Schulnummer
Typ | A<br/>
Größe| 8<br/>
Bemerkung|Schulnummer

Die maximale Größe der Schulnummer sind demnach 8 Zeichen. Die Schulnummer
1234567890 wird z.B. nicht importiert und Sie erhalten eine entsprechende Fehlermeldung.


## Was sollten Sie vor dem Import beachten?


 ### Zeiträume anlegen

Klassen- und Schülerdaten erfordern Zeiträume in Form von Halbjahren. Bitte tragen Sie vor dem Import dieser Daten entsprechend des MAGELLAN-Handbuchs alle notwendigen Zeiträume in MAGELLAN ein. 
Besonderheit des Imports: Die Halbjahre müssen wie folgt lauten:
1. HJ: 01.08.XXXX – 31.01.XXXX
2. HJ: 01.02.XXXX – 31.07.XXXX

### Import der Schlüsselverzeichnisse

Bevor Sie Daten nach Magellan importieren, sollten Sie bereits die "Schlüsselverzeichnisse" Ihres Bundeslandes importiert und ggf. zu importierende Felder in den Quelldaten daran angepasst haben.

Ein Beispiel: 

Für Ihr Bundesland existiert das Schlüsselverzeichnis „Konfessionen“. Wenn Sie die Schlüsselverzeichnisse eingelesen haben, dann gibt es beispielsweise bereits den Wert „rk“ für römisch-katholisch, mit dem damit verbundenen Statistikschlüssel.

Damit beim Import der Schülerdaten auf diese bereits bestehende Konfession verwiesen werden kann, muss in Ihrer Importdatei in der Spalte „Konfession“ das Kürzel „rk“ verwendet werden, anderenfalls würde der abweichende Wert als zusätzlicher Eintrag in Ihrem Schlüsselverzeichnis in Magellan hinzugefügt werden, leider ohne einen Statistikschlüssel, da dieser beim Import nicht ersichtlich ist.

Wie Sie die Schlüsselverzeichnisse Ihres Bundeslandes nach Magellan einlesen, entnehmen Sie bitte dem Abschnitt [Schlüsselverzeichnisse importieren](https://doc.magellan7.stueber.de/schulverwaltung/admin/datenaustausch/#kataloge-schlusselverzeichnisse-importieren) der allgemeinen [MAGELLAN-Dokumentation](https://doc.magellan7.stueber.de/).

### Weitere wichtige Einstellungen

Zusammengefasst müssen Sie beim Import für jede Datei Folgendes beachten:

* Jede Datei besitzt in der ersten Zeile eine Kopfzeile, in der die verwendeten Felder angegeben sind.

* Mindestens die Pflichtfelder einer Datei müssen für jede zu importierende Zeile angeben sein, da sonst die Daten nicht eingelesen werden.

* Die Reihenfolge der Felder einer Datei spielt keine Rolle für den Import.

# Importschnittstelle

Die Importschnittstelle besteht aus Importdateien, die in einer festgelegten Semantik vorliegen müssen. Im folgenden Abschnitt wird erklärt, wie die Importdateien genau auszusehen haben und welche Felder vorhanden sein müssen, damit der Import korrekt durchlaufen kann. Die Verwendung des Import-Format-Assistenten beschreiben wir im Abschnitt ["Importieren mit dem Importassistenten"](importieren_mit_dem_importassistenten.md).

## Schnittstellenformate

* [schulen.import.csv](schnittstellenformat_schulenimportcsv.md)
* [betriebe.import.csv](betriebeimportcsv.md)
* [lehrer.import.csv](lehrerimportcsv.md)	
* [schueler.import.csv](schuelerimportcsv.md)
* [sorgebe.import.csv](sorgebeimportcsv.md)	
* [verlage.import.csv](verlageimportcsv.md)
* [lieferanten.import.csv](lieferantenimportcsv.md)	
* [medien.import.csv](medienimportcsv.md)
* [exemplare.import.csv](exemplareimportcsv.md)	
* [klassen.import.csv](klassenimportcsv.md)
* [schueler_laufbahn.import.csv](schuelerlaufbahn_importcsv.md)
* [schueler_fachdaten.import.csv](schuelerfachdatenimportcsv.md)
* [schueler_sorgebe.import.csv](schuelersorgebeimportcsv.md)
* [schueler_schulen.import.csv](schuelerschulenimportcsv.md)
* [schueler_ausbildung.import.csv](schuelerausbildungimportcsv.md)
