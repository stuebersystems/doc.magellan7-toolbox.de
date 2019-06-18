# SPlan

Die Datenübernahme aus dem Schulverwaltungsprogramm SPlan ermöglicht je nach Version verschiedene Daten nach MAGELLAN zu übernehmen. Aktuell unterstützen wir die Konvertierung von SPlan 2004. Auf Anfrage ermöglichen wir Ihnen die Konvertierung und Übernahme weiterer SPlan Versionen nach MAGELLAN.

SPlan Daten werden über den Export der Daten aus SPlan übernommen. Somit stehen für den Import auch nur die Daten zur Verfügung, die SPlan in diese Datei(en) exportiert. Die SPlan Exportdateien werden über den MAGELLAN-Importformatkonverter ausgelesen und in das MAGELLAN-Importformat konvertiert. Danach können die Daten in diesem Standardformat nach Magellan importiert werden.
Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Export, die Konvertierung und den Datenimport aus dem Schulverwaltungsprogramm SPlan nach MAGELLAN. 

Der Import erfolgt in fünf Schritten:

1. Vorbereiten der MAGELLAN-Datenbank und Daten
2. Export der Daten aus SPlan.
3. Konvertieren in das MAGELLAN-Importformat.
4. Manuelle Anpassungen
5. Import der Daten nach MAGELLAN

## Übersicht der Importdateien und MAGELLAN-Importformate

Importdatei	|IBIS-Datenbank	|Beschreibung
--|--|--|
**sorgebe.import.csv**|	SCHULEXP.CSV|	Enthält die Stammdaten der Sorgeberechtigten
**schueler.import.csv**|	SCHULEXP.CSV	|Enthält die Stammdaten der Schüler
**schueler_sorgebe.import.csv	**|SCHULEXP.CSV	|Enthält die Zuordnung der Sorgeberechtigten zu den Schülern<br/>Weitere Bedingung: <br/>Import der sorgebe.import.csv<br/>Import der schueler.import.csv

## Schritt 1: Vorbereiten der MAGELLAN-Datenbank und Daten

Für den Import von Daten muss die MAGELLAN-Datenbank vorbereitet werden.

### MAGELLAN-Datenbank leeren

Üblicherweise liefert STÜBER SYSTEMS eine Datenbank mit Beispielinhalten. Diese Daten müssen vor dem Import gelöscht werden. Dazu gehen Sie bitte wie folgt vor.

1. Starten Sie den MAGELLAN-Administrator. 
2. Wählen Sie die Ansicht ```Datenbankpflege``` und führen Sie ```Datenbankinhalt löschen``` aus.

Es werden alle Beispieldaten, Schlüsselverzeichnisse und Postleitzahlen gelöscht.

### Schlüsselverzeichnisse importieren

Importieren Sie die in MAGELLAN mitgelieferten Schlüsselverzeichnisse für Ihr Bundesland nach MAGELLAN. Gehen Sie dabei wie folgt vor.

1. Starten Sie den MAGELLAN-Administrator. 
2. Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Schlüsselverzeichnisse importieren``` aus. Geben Sie als Parameter ihr Bundesland, Ihre Schulart, den Mandanten und Alle Kataloge an.
3. Nach dem Import der Schlüsselverzeichnisse wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Postleitzahlen importieren``` aus. Geben Sie als Parameter ihr``` Land/Bundesland``` und den ```Mandanten``` an. 

### Daten vorbereiten

Die in SPlan exportierten Daten sind in einigen Feldern Langbezeichnungen. Bei Feldern, die auf Schlüsselverzeichnisse verweisen wird für den Import aber ein Kürzel benötigt. Sie sollten sich nach dem Export der Daten diese in einem Texteditor ansehen und die entsprechenden Felder entweder bereits in SPlan entsprechend dem Magellan-Importformat bzw. der Schlüsselverzeichnisse Ihres Bundeslandes abändern und den Export wiederholen oder nach der Konvertierung der Daten in den Dateien des MAGELLAN-Importformats ändern. 

Ein Beispiel sind die Länderbezeichnungen der Staatsangehörigkeit. Dort exportiert SPlan für Deutschland den Wert „Deutschland“. In MAGELLAN werden Geburtsländer aus dem Verzeichnis „Staatsagenhoerigkeiten“ ausgelesen, dessen Wert für die Eindeutigkeit das Kürzel darstellt.
Das Kürzel für Deutschland ist in den meisten Fällen der statistische Schlüssel „000“. Für diesen Fall korrigiert der Importformat Konverter den Wert „Deutschland“ nach „000“, dies kann aber nicht für alle anderen möglichen Länderbezeichnungen und eventuellen Werte anderer Importfelder, die auf weitere Schlüsselverzeichnisse geschehen. Aus diesem Grunde muss manuell vorbereitet, oder nach der Konvertierung nachgebessert werden.

## Schritt 2: Export der Daten aus SPlan

Je nach SPlan-Version können Sie die Daten in das CSV-Format oder als Exceldatei abspeichern. Das CSV-Format wird bevorzugt.

Zum Export der Daten gehen Sie in S-Plan wie folgt vor:

1. Rufen Sie SPlan auf.
2. Wählen Sie den Bereich ```Schüler```.
3. Wählen Sie ```Bearbeiten```, dann ```Filter und Export```, dann ```Export Gesamtdaten``` und dann ```Alle Schüler der Schule (CSV)```.
4. Ab der SPLAN2005 Version ist es möglich Betriebe und Schuldaten nach Magellan zu übernehmen. Zum Export der Betriebe und Schuldaten gehen Sie in SPlan wie folgt vor:
5. Rufen Sie SPlan auf.
6. Wählen Sie den Bereich ```Betriebe & Schulpartner```.
7. Wählen Sie ```Bearbeiten```, dann ```Filter und Export```, dann ```Export aller Daten```.

>WICHTIG<br/>
Wenn Sie die Daten als Excel Datei exportieren, muss für die Konvertierung der Daten Excel auf dem Rechner installiert sein.

## Schritt 3: Konvertieren in das MAGELLAN-Importformat

Navigieren Sie im Importformatkonverter über die Schalflächen „Zurück“ und „Weiter“, um zu den entsprechenden Seiten des Assistenten zu gelangen.

1. Starten Sie den MAGELLAN-Importformatkonverter über den Explorer. Rufen Sie dazu die Datei MagellanIFConv.exe im Programmordner von MAGELLAN (z.B. C:\Stueber Software\Magellan 6\MagellanIFConv.exe).
2. Seite **Anwendung** – In der Auwahlbox für das Programm wählen Sie ```SPlan``` aus und das verwendete Trennzeichen der CSV-Datei.
3. Seite **Quelle/Ziel** – Wählen Sie für die Quelldatei den Konvertierungstyp ```Schulexport``` und die zuvor aus SPlan exportierte Datei aus. 
4. Seite **Quelle/Ziel** – Geben Sie in das untere Feld den Pfad an, in dem die konvertierten Magellan-Importformat Dateien abgespeichert werden sollen.
5. Seite **Der Assistent ist bereit** – Klicken Sie auf ```Fertigstellen```, um die Konvertierung zu starten.

Nach der Konvertierung liegen die MAGELLAN-Importformat Dateien im .CSV-Format in dem von Ihnen angegebenen Dateipfad.

## Schritt 4: Manuelle Anpassungen

Format erhalten. Diese Textdateien können mit einem Texteditor oder einem Tabellenkalkulationsprogramm (Wir empfehlen Libre- oder OpenOffice wg. der Unterstützung des CSV-Formats) öffnen und bearbeiten. 

An dieser Stelle haben Sie die Möglichkeit, sich die Daten vor dem Import anzusehen und ggf. Ände-rungen manuell einzubringen. Wie unter Daten vorbereitenDaten vorbereiten bereits beschrieben können Sie hier ggf. Daten die nicht korrekt importiert würden korrigieren.



## Schritt 5: Daten nach MAGELLAN importieren

1. Starten Sie den MAGELLAN-Administrator.
2. Wählen Sie die Ansicht ```Datenimporte``` und führen Sie Daten über ```MAGELLAN-Importformat importieren``` aus.
3. Lesen Sie bitte im Kapitel „MAGELLAN-Importformat“, wie Sie die Daten korrekt  nach Magellan importieren.

## Übersicht der unterstützten SPlan Daten und Importfelder

In der nachfolgend aufgelisteten Tabelle erhalten Sie eine Übersicht der Daten, die für den Import von SPlan nach MAGELLAN über das allgemeine Importformat und dem Importformatkonverter bereits unterstützt werden. Ausgenommen sind zusätzliche Felder, die Sie evtl. manuell in die Importdateienhinzufügen.

Für die Konvertierung/Import benötigte Pflichtfelder werden hervorgehoben dargestellt.

###SCHULEXP.CSV
In der SCHULEXP.CSV Datei befinden sich die Stammdaten der Schüler, Sorgeberechtigte und die Verbindung zu Schüler-Sorgeberechtigten.

Feld in der Datei|	Bedeutung	|Anmerkung zur Übernahme
--|--|--
Anrede	|Anrede des Schülers|	**Herrn** und **Frau** wird konvertiert
**Name**|	Nachname des Schülers| 	 
**Vorname**	|Vorname des Schülers	 
**GebDat**|	Geburtsdatum des Schülers	 
Geburtsname	|Geburtsname des Schülers	 
GebOrt	|Geburtsort des Schülers	 
GebLandKreis|	Geburtsland des Schülers	 
Strasse|	Strasse des Schülers	
PLZOrt	|PLZ und Ort des Schülers	|**PLZ** und **Ort** werden getrennt, wenn die ersten 5 Zeichen Zahlen sind, Beispiel: „12345 Ortsname“, ansonsten wird der komplette Wert beim Ort gespeichert.
Ortsteil	|Ortsteil des Schülers	
Telefon|	Telefon des Schülers	
Staat	|Wohnort Land des Schülers	|Es wird ein Kürzel entsprechend dem Verzeichnis „Staatsangehörigkeiten“ erwartet.
Geschlecht|	Geschlecht des Schülers	
Nation|	Staatsangehörigkeit des Schülers	|Es wird ein Kürzel entsprechend dem Verzeichnis „Staatsangehörigkeiten“ erwartet.
Konfession|	Konfession des Schülers	|Es wird ein Kürzel entsprechend dem Verzeichnis „Konfessionen“ erwartet.
ReligUnterIn	|Teilnahme am Religionsunterricht|	Es wird ein Kürzel entsprechend dem Verzeichnis „Religion (Teilnahmen)“ erwartet.
DatRelAbmeld|	Von-Datum der Abmeldung am Religionsunterricht	
Vorbildung|	Höchster allgemeinbildender Abschluss|	Es wird ein Kürzel entsprechend dem Verzeichnis „Abschluesse (extern)“ erwartet.
DatumEinschl	|Datum des Zugangs des Schülers an der Schule	
DatEntlassung|	Datum der Entlassung des Schülers von der Schule	
Aussiedler	|Aussiedlerstatus des Schülers	
Sprache1	|1. Fremdsprache	|Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
Sprache2|	2. Fremdsprache	|Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
Sprache3	|3. Fremdsprache|	Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
EintrGrundAm|	Datum des Grundschuleintritts	
Wahlfach1	|1. Wahlfach|	Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
Wahlfach2	|2. Wahlfach|	Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
Wahlfach3	|3. Wahlfach|Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
Wahlfach4	|4. Wahlfach|	Es wird ein Kürzel entsprechend dem Verzeichnis „Faecher“ erwartet.
privateMail|	Email-Adresse des Schülers	
ArtEltern1, ArtEltern2	|Sorgeberechtigten Verhältnis zum Schüler|	Aktuell werden die Verhältnisse wie folgt konvertiert:<br/>	V	Vater<br/>		M	Mutter<br/>		E	Eltern
TitelEltern1, TitelEltern2	|Anrede des Sorgeberechtigten	
NameEltern1, NameEltern2|	Nachname des Sorgeberechtigten	
VornameEltern1, VornameEltern2|	Vorname des Sorgeberechtigten	
StrasseEltern1, StrasseEltern2	|Strasse des Sorgeberechtigten	
PLZOrtEltern1, PLZOrtEltern2	|PLZ und Ort des Sorgeberechtigten|	**PLZ** und **Ort** werden getrennt, wenn die ersten 5 Zeichen Zahlen sind, Beispiel: „12345 Ortsname“, ansonsten wird der komplette Wert beim Ort gespeichert.
TelefonEltern1,TelefonEltern2	|Private Telefonnummer des Sorgeberechtigten	
