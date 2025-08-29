# Einführung

Magellan kann Daten aus entsprechend aufbereiteten CSV-Dateien übernehmen. In diesem Dokument finden Sie dazu die nötigen Informationen, um den Import erfolgreich durchführen zu können. Lesen Sie sich die entsprechenden Abschnitte sorgfältig durch, um mögliche Fehler zu vermeiden.

## Daten selbst übernehmen

Wenn Sie selbst Daten nach Magellan übernehmen wollen, stehen Ihnen mehrere Wege zur Verfügung:

* Mit Hilfe von Microsoft Access können Sie direkt auf die Datenbanktabellen von Magellan zugreifen. Damit haben Sie die Möglichkeit, Daten aus anderen Datenquellen in die entsprechenden Tabellen zu importieren.

* Sie bringen die Daten, die Sie nach Magellan übernehmen wollen in das Magellan-Importformat beschriebene Format und importieren die Daten mit Hilfe des Magellan-Administrators.

* Sie nutzen die Magellan-Skripting-Technologie. Dies hat den Vorteil, dass Sie die Datenübernahme genau nach Ihren Wünschen durchführen können. Sie müssen sich jedoch in diesem Fall mit der Programmiersprache der Magellan-Skripte und der Datenstruktur von Magellan beschäftigen.

Für welche Form des Imports Sie sich letztendlich entscheiden, hängt hauptsächlich von Ihren Vorkenntnissen und der Ihnen zur Verfügung stehenden Zeit ab.

## Daten von STÜBER SYSTEMS übernehmen lassen

Auf Wunsch übernimmt STÜBER SYSTEMS für Sie gegen Berechnung die Daten aus Ihrem Altsystem. Schicken Sie dazu bitte Ihre Daten und die nötigen Informationen zum Altprogramm. Wir erstellen für Sie ein entsprechendes Angebot für die Datenübernahme.

Auf Wunsch bieten wir Ihnen unser **`Basispaket Datenübernahme`**
 an.

Das Paket besteht aus:

* einer detaillierten Datenanalyse: Prüfung der erzeugten
 Importformat-Dateien, Rückmeldung an Kunden bzgl.
 voraussichtlich relevanter Probleme

* der Erstellung einer vorbereiteten Datenbank mit
 Schlüsselverzeichnissen des Bundeslandes und der
 Schulart (soweit vorhanden),

* dem Einspielen der erstellten Magellan-Importformat-Dateien in eine Kopie der vorbereiteten Datenbank (abhängig von der Qualität der Ausgangsdaten),

* ggfs. der Erweiterung/Anpassung des Importprojektes im Magellan-DataCenter] Zusätzlich können Sie unsere Unterstützung per Teamviewer oder telefonisch für die individuelle Datenanpassung buchen.

!!! warning "Wichtig"

    Wir nehmen keine Korrekturen an den Daten der Kunden vor. Diese Leistung muss vom Kunden übernommen werden. Auf explizite Anfrage im Rahmen der 5 Stunden können konkrete Datenbestände angepasst werden. Wir ändern auf unsere Verantwortung hin keine einzelnen Datenwerte ab, da wir für die Richtigkeit der Daten keine Gewähr geben können und auch von uns aus keine Bewertung über die Richtigkeit der Daten machen können.

## Magellan-Skriptingtechnologie

Eine Datenübernahme aus einer anderen Anwendung nach Magellan ist auch mit Hilfe der Magellan-Skripting-Technologie möglich. Dies hat den Vorteil, dass Sie die Datenübernahme genau nach Ihren Wünschen durchführen können. Sie müssen sich jedoch in diesem Fall mit der Programmiersprache der Magellan-Skripte und der Datenstruktur von Magellan beschäftigen.

Bei einer Datenübernahme über das Magellan-Importformat entfällt der Aufwand der Programmierung. Jedoch müssen Sie Ihre Daten zunächst in das geforderte Magellan-Importformat bringen. Zusätzlich sind Sie auf die im Magellan-Importformat enthaltenen Felder eingeschränkt, die nur eine Teilmenge aller Datenfelder der Magellan-Datenstruktur darstellen.

Für welche Form des Imports Sie sich letztendlich entscheiden, hängt hauptsächlich von Ihren Vorkenntnissen und der Ihnen zur Verfügung stehenden Zeit ab.

## Magellan-Importformat

Das Magellan-Importformat ermöglicht den Import von Daten aus Textdateien nach Magellan. Diese Textdateien müssen dazu dem im Folgenden beschriebenen Format entsprechen. Der eigentliche Import erfolgt mit Hilfe des Magellan-Administrators.

### Übersicht der Importdateien

Jede Datei muss wie in der Spalte „Importdatei“ der folgenden Auflistung benannt sein. Die Dateien sind in der empfohlenen Importreihenfolge aufgelistet. Die Importreihenfolge ist wichtig für die Dateien, die auf zuvor importierte Daten zurückgreifen müssen.

**Beispiel:**

Die Datei „schueler_sorgebe.import.csv“ kann nur sinnvoll importiert werden, wenn zuvor die Dateien „sorgebe.import.csv“ und „schueler.import.csv“ importiert wurden.

Importdatei|Beschreibung
---|---
[schulen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schnittstellenformat_schulenimportcsv)|Enthält die Stammdaten der Schulen
[betriebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/betriebeimportcsv)|Enthält die Stammdaten der Betriebe
[lehrer.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/lehrerimportcsv)|Enthält die Stammdaten der Lehrer
[schueler.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerimportcsv)|Enthält die Stammdaten der Schüler und Bewerber
[sorgebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/sorgebeimportcsv)|Enthält die Stammdaten der Sorgeberechtigten
[verlage.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/verlageimportcsv)|Enthält die Stammdaten der Verlage
[lieferanten.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/lieferantenimportcsv)|Enthält die Stammdaten der Lieferanten
[medien.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/medienimportcsv)|Enthält die Stammdaten der Medien

Alle nachfolgenden Dateien verbinden vorab importierte Daten miteinander:

Importdatei|Beschreibung
---|---
[exemplare.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/exemplareimportcsv)|Enthält die Exemplardaten zu den Medien<br/>Bedingung:<br/> Import der medien.import.csv
[klassen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/klassenimportcsv)|Enthält die Stamm- und Zeitraumdaten der Klassen<br/>Bedingung: <br/>Vorhandensein der Zeiträume und Lehrer (Verweis auf Klassenleiter) in Magellan.
[schueler_laufbahn.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerlaufbahn_importcsv) |Enthält die Laufbahndaten der Schüler <br/>Weitere Bedingung: <br/>Import der klassen.import.csv und schueler.import.csv
[schueler_fachdaten.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerfachdatenimportcsv) |Enthält die Fachdaten der Schüler<br/>Weitere Bedingung:<br/> Import der klassen.import.csv, schueler.import.csv und schueler_laufbahn.import.csv
[schueler_sorgebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelersorgebeimportcsv)|Enthält die Zuordnung der Sorgeberechtigten zu den Schülern<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und sorgebe.import.csv
[schueler_schulen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerschulenimportcsv)|Enthält die bereits besuchten Schulen der Schüler (Stichwort: Herkunftsschulen)<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und schulen.import.csv
[schueler_ausbildung.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerausbildungimportcsv)|Enthält die Ausbildungsdaten der Schüler<br/>Weitere Bedingung:<br/> Import der schueler.import.csv und betriebe.import.csv

!!! warning "Wichtig"

    Reihenfolge des Einlesens: 
    Da die Importdateien teilweise aufeinander aufbauende Daten enthalten, empfehlen wir die obenstehende Reihenfolge beim Import einzuhalten.

### Aufbau der Importdateien

Jede dieser Dateien muss als CSV-Datei mit der Codierung UTF-8 aufgebaut sein, d.h. sie besteht jeweils aus einer Kopfzeile und ein oder mehreren Zeilen mit den zu importierenden Inhalten. Die einzelnen Felder sind durch Semikolon getrennt und mit Anführungszeichen abgegrenzt.

!!! note "Hinweis!"    

    Speichern Sie Ihre Daten aus dem Standardeditor `Notepad` heraus, so können Sie eine Datei mit `Speichern unter` und der Codierung `UTF-8` erzeugen.


Die Schülerdatei kann z.B. folgenden Aufbau haben

`„Nachname“;„Vorname“;„Anrede“;„Geschlecht“;„Strasse“;` <br/>
 `„Müller“;„Hans“;„H“;„m“;„Mühlenweg 11“`<br/>
 `„Meier“;„Petra“;„F“;„w“;„Mühlenweg 12“`

Die Reihenfolge der Felder spielt dabei keine Rolle. Die Semantik der Felder wird durch die Kopfzeile bestimmt. Beispielsweise kann auch eine Schülerdatei mit folgendem Aufbau eingelesen werden.

`„Strasse“;„Geschlecht“;„Vorname“;„Nachname“;„Anrede“`<br/>
`„Mühlenweg 11“;„m“;„Müller“;„Hans“;„H“`<br/>
`„Mühlenweg 12“;„w“;„Meier“;„Petra“;„F“`

Die Felder entsprechen dem sog. System Data Format (SDF), d.h. bei einem Semikolon, Komma, Sonderzeichen oder einem Leerzeichen im String wird der String in Anführungszeichen gesetzt, z.B. die Strasse "Mühlenweg 11" wird<br/><br/>
`;“Mühlenweg 11“;...`<br/>
und nicht<br/>
`;Mühlenweg 11;...`

geschrieben.

Besitzt der Inhalt selbst Anführungszeichen, so sind doppelte Anführungszeichen anzugeben. Wollen Sie z.B. “Hallbach“ einlesen, so müssen Sie als Inhalt<br/>
`;““Hallbach““;...`

angeben.
Welche Felder pro Datei eingelesen werden, ist den nachfolgenden Abschnitten pro Datei zu entnehmen.

!!! warning "Wichtig"

    Die CSV-Dateien müssen im UTF-8 Format abgespeichert sein! Ein Einlesen im ANSI-Format wird nicht unterstützt.

!!! warning "Wichtig"

    Zeilenumbrüche sind in einer CSV-Datei nicht erlaubt. Das Datenformat bestimmt jede Zeile als einen Datensatz. Ein Umbruch mitten in der Zeile kann nicht verarbeitet werden. Wir erlauben in den Feldern, die mit dem Datentyp M für Memofeld gekennzeichnet sind Zeilenumbrüche in Form der Notation: \n. Beim Import wird diese Notation in einen echten Zeilenumbruch umgewandelt.

### Datentypen

Bei der Beschreibung finden folgende Datentypen Verwendung

Typ|Beschreibung
---|---
A|Textfeld mit maximaler Länge (Textfeld)
D |Datumsangabe , Format: TT.MM.JJJJ (Datumsfeld)
I |Ganze Zahl (32-Bit-Integer
L |Logisches Feld: Textfeld der Größe 1 mit den möglichen Werten "J" oder "N"
M |Textfeld mit variabler Länge (Memofeld)
N |Kommazahl (Numeric) z.B. „2,5“ oder „2.5“
S |Ganze Zahl (16-Bit-Integer)

Einige Felder haben auch eine bestimmte Funktion in der Datei und werden als Zusatz zum Typ dargestellt. Diese Funktion wird ebenfalls durch ein zusätzliches Kürzel gekennzeichnet.

Typ|Beschreibung
---|---
P|Pflichtfeld. Es muss mindestens pro Datensatz gefüllt sein, damit der Datensatz importiert werden kann.
P2 |Sekundärpflichtfelder. Diese sind für den Import insoweit relevant, dass wir Felder mit P und P2 berücksichtigen, wenn wir überprüfen, ob ein Datensatz bereits existiert. Für den Import selbst, sind Eingaben in P2 Felder dann nicht relevant. Relevant wird es, wenn Verweise auf Tabellen mit P2 Feldern existieren. Denn dann kann ein Import dieser Verweise nur gewährleistet werden, wenn P1 und P2 Felder übereinstimmen.
V |Verweis. Gibt an, dass der eigentliche Stammsatz in einer anderen Tabelle liegt und hier nur der Verweis darauf gespeichert ist. Dies kann eine Zahl (ID) sein, oder ein Textkürzel.

!!! warning "Wichtig"

    Pflichtfelder müssen angegeben werden, andere Felder können angegeben werden. Die Kombination der Inhalte der Pflichtfelder einer Datei muss eindeutig sein. Ist keine oder nur eine Untermenge der Pflichtfelder angegeben, erfolgt kein Import.

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

### Was sollten Sie vor dem Import beachten

#### Zeiträume anlegen

Klassen- und Schülerdaten erfordern Zeiträume in Form von Halbjahren. Bitte tragen Sie vor dem Import dieser Daten entsprechend des Magellan-Handbuchs alle notwendigen Zeiträume in Magellan ein.
Besonderheit des Imports: Die Halbjahre müssen wie folgt lauten:

1. HJ: 01.08.XXXX – 31.01.XXXX
2. HJ: 01.02.XXXX – 31.07.XXXX

#### Import der Schlüsselverzeichnisse

Bevor Sie Daten nach Magellan importieren, sollten Sie bereits die "Schlüsselverzeichnisse" Ihres Bundeslandes importiert und ggf. zu importierende Felder in den Quelldaten daran angepasst haben.

Ein Beispiel:

Für Ihr Bundesland existiert das Schlüsselverzeichnis „Konfessionen“. Wenn Sie die Schlüsselverzeichnisse eingelesen haben, dann gibt es beispielsweise bereits den Wert „rk“ für römisch-katholisch, mit dem damit verbundenen Statistikschlüssel.

Damit beim Import der Schülerdaten auf diese bereits bestehende Konfession verwiesen werden kann, muss in Ihrer Importdatei in der Spalte „Konfession“ das Kürzel „rk“ verwendet werden, anderenfalls würde der abweichende Wert als zusätzlicher Eintrag in Ihrem Schlüsselverzeichnis in Magellan hinzugefügt werden, leider ohne einen Statistikschlüssel, da dieser beim Import nicht ersichtlich ist.

Wie Sie die Schlüsselverzeichnisse Ihres Bundeslandes nach Magellan einlesen, entnehmen Sie bitte dem Abschnitt [Schlüsselverzeichnisse importieren](https://doc.magellan7.stueber.de/schulverwaltung/admin/datenaustausch/#kataloge-schlusselverzeichnisse-importieren) der allgemeinen [Magellan-Dokumentation](https://doc.magellan7.stueber.de/).

#### Weitere wichtige Einstellungen

Zusammengefasst müssen Sie beim Import für jede Datei Folgendes beachten:

* Jede Datei besitzt in der ersten Zeile eine Kopfzeile, in der die verwendeten Felder angegeben sind.

* Mindestens die Pflichtfelder einer Datei müssen für jede zu importierende Zeile angeben sein, da sonst die Daten nicht eingelesen werden.

* Die Reihenfolge der Felder einer Datei spielt keine Rolle für den Import.

## Importschnittstelle

* [schueler_ausbildung.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerausbildungimportcsv)
Die Importschnittstelle besteht aus Importdateien, die in einer festgelegten Semantik vorliegen müssen. Im folgenden Abschnitt wird erklärt, wie die Importdateien genau auszusehen haben und welche Felder vorhanden sein müssen, damit der Import korrekt durchlaufen kann. Die Verwendung des Import-Format-Assistenten beschreiben wir im Abschnitt ["Importieren mit dem Importassistenten"](https://doc.magellan-toolbox.stueber.de/importe/MagImp/importieren_mit_dem_importassistenten).

### Schnittstellenformate

* [schulen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schnittstellenformat_schulenimportcsv)
* [betriebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/betriebeimportcsv)
* [lehrer.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/lehrerimportcsv)
* [schueler.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerimportcsv)
* [sorgebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/sorgebeimportcsv)
* [verlage.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/verlageimportcsv)
* [lieferanten.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/lieferantenimportcsv)
* [medien.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/medienimportcsv)
* [exemplare.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/exemplareimportcsv)
* [klassen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/klassenimportcsv)
* [schueler_laufbahn.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerlaufbahn_importcsv)
* [schueler_fachdaten.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerfachdatenimportcsv)
* [schueler_sorgebe.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelersorgebeimportcsv)
* [schueler_schulen.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerschulenimportcsv)
* [schueler_ausbildung.import.csv](https://doc.magellan-toolbox.stueber.de/importe/MagImp/schuelerausbildungimportcsv)
