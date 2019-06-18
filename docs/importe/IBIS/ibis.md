# IBIS 

Die Datenübernahme aus dem Schulverwaltungsprogramm IBIS ermöglicht den Import von Fächer-, Betriebe-, Sorgeberechtigte-,  Schüler- (inkl. Herkunft, Ausbildung und Verbindung Schüler-Sorgeberechtige), Klassen- und Lehrerdaten nach Magellan. Die IBIS FoxPro Datenbankdateien (im .DBF-Format) können über den Magellan-Importformatkonverter ausgelesen und in das Magellan-Importformat konvertiert werden. 
Der Import erfolgt in sechs Schritten:
1.	Konvertieren in das Magellan-Importformat
2.	Konvertierte Daten korrigieren
3.	Manuelle Anpassungen
4.	Vorbereiten der Magellan-Datenbank
5.	Import der Daten nach Magellan
6.	Bereinigen von Importartefakten


## Übersicht der Importdateien und Magellan-Importformate

Importdatei	|IBIS-Datenbank|	Beschreibung
--|--|--
**betriebe.import.csv **|FIRMEN.DBF|Enthält die Stammdaten der Betriebe
**lehrer.import.csv**|	LEHRER.DBF <br>KLASSEDE.DBF	|Enthält die Stammdaten der Lehrer
**sorgebe.import.csv	**|IBISEKEY.DBF	|Enthält die Stammdaten der Sorgeberechtigten
**klassen.import.csv**|	KAR3PKEY.DBF <br>KLASSEDE.DBF|	Enthält die Stamm- und Zeitraumdaten der Klassen<br/>Bedingung: Vorhandensein der Zeiträume in MAGELLAN.
**schueler.import.csv**	|IBISEKEY.DBF	|Enthält die Stammdaten der Schüler und Bewerber
**schueler_laufbahn.import.csv**	|KAR3PKEY.DBF|	Enthält die Laufbahndaten der Schüler <br/>Weitere Bedingung: Import der klassen.import.csv
**schueler_fachdaten.import.csv**	|KAR3PKEY.DBF<br/>KAR3PKEY.FPT|	Enthält die Fachdaten der Schüler Wichtig: Die KAR3PKEY.FPT Datei enthält die Noten der Schüler.
**schueler_sorgebe.import.csv**	|IBISEKEY.DBF	|Enthält die Zuordnung der Sorgeberechtigten zu den Schülern<br/>Weitere Bedingung: Import der sorgebe.import.csv
**schueler_schulen.import.csv**	|IBISEKEY.DBF|	Enthält die bereits besuchten Schulen der Schüler (Stichwort: Herkunftsschulen)<br/>Weitere Bedingung: Import der schulen.import.csv
**schueler_ausbildung.import.csv**|	IBISEKEY.DBF	|Enthält die Ausbildungsdaten der Schüler<br/>Weitere Bedingung: Import der betriebe.import.csv
**00_Faecher.keys	**|FACHDEF.DBF|	Enthält die Fächer.<br/>Weitere Bedingung: Muss als Schlüsselverzeichnis vor allen anderen Importdateien importiert werden.


## Voraussetzungen

Wichtig für die Übernahme von IBIS-Daten ist die vollständige Erfassung der Daten in IBIS an bestimmten Stellen. 

* Zur Erfassung vollständiger Lehrerdatensätze muss die Datenbank LEHRER.DBF vorhanden und gepflegt sein. Andernfalls wird nur der Lehrerkürzel aus der KLASSEDE.DBF übernommen.
* Zur Erfassung der Klassen in den Zeiträumen, Schülerlaufbahnen und den entsprechenden Schülerfachdaten muss die KAR3PKEY.DBF mit den Eintritts- und Austrittsdaten der Schüler in die Klassen vollständig gefüllt sein. Andernfalls wird die Laufbahn falsch abgebildet. Bei der Konvertierung wird auch eine weitere CSV-Datei ausgespielt, die zur Kontrolle der fehlerhaften Laufbahnen dienen.<br/>Die Datei ```Fehlerhafte Laufbahndaten in IBIS.csv``` enthält einen Ausschnitt der fehlerhaften Laufbahndaten, die nicht zugeordnet werden können. Entschließen Sie sich die fehlerhaften Laufbahndaten zu ignorieren und die erstellte schueler_laufbahn.import.csv Datei zu importieren, dann werden Ihre Schülerlaufbahnen mit höchster Wahrscheinlichkeit inkorrekt und unvollständig sein. Diese lassen sich im Nachhinein auch nicht in Magellan korrigieren. Aus diesem Grund empfehlen wird dringend alle IBIS Laufbahndaten von vornherein nachzupflegen und erst dann den Import durchzuführen. Zur Unterstützung wird beim Konvertieren der Daten versucht einige Zeiträume von vornherein zu korrigieren. Die Korrekturregeln lauten dabei wie folgt:
  * Es wird das Austrittsdatum aus der Klasse korrigiert, wenn  das Eintrittsdatum vorhanden und das Austrittsdatum leer ist.
  * Die Korrektur setzt das Austrittsdatum auf das Endddatum der Klasse, wenn das Enddatum der Klasse nicht größer als das Eintrittsdatum des nächsten Laufbahndatensatzes des Schüler ist. In dem Falle wird das Eintrittsdatum - 1 Tag gerechnet und als Austrittsdatum verwendet.
  * Eintritts- und Austrittsdaten orientieren sich an der Datumsangabe 01.08., beginn des 1.Halbjahres eines Schuljahres. Wenn entsprechend das Eintrittsdatum davor oder danach liegt wird das passende Schuljahr dazu berechnet.
* Da IBIS die Unterscheidung zwischen Klassenzeiträumen und Schülerzeiträumen nicht kennt, kann es vorkommen, dass Sie Klassen erhalten, die z.B. einen Bestand von 10 Jahren und mehr haben können und damit wären auch die Schüler solange in diesen Klassen. Das passiert dann, wenn kein Schüler einer solchen Klasse ein Austrittsdatum eingetragen hat, aber das kleinste Eintrittsdatum  schon sehr lange zurückliegt. Wenn Sie für eine solche Klasse an einer Stelle in IBIS bei einem Schüler dieser Klasse ein Austrittsdatum setzen, dann erhalten alle Schüler dieser Klasse automatisch das Austrittsdatum dieser Klasse und Sie hätten mit geringem Aufwand Ihre Datenlage verbessert.

> #### warning::Wichtig!
>
> Bitte beachten Sie, dass der Import für aktuelle oder Archivdaten ausgelegt ist, damit keine zukünftigen Zeiträume in MAGELLAN befüllt werden können.

## Schritt 1: Konvertieren in das MAGELLAN-Importformat

Navigieren Sie im Importformatkonverter über die Schalflächen „Zurück“ und „Weiter“, um zu den entsprechenden Seiten des Assistenten zu gelangen. Wenn Sie die Konvertierung starten, werden zuerst die Spaltennamen und die Pflichtfelder überprüft. Treten keine Probleme auf, werden die Quelldaten in die Zieldatei übernommen.
1.	Liegen Ihre IBIS-Datenbanken unverschlüsselt vor? Wenn Sie sich nicht sicher sind, lesen Sie bitte die untere Informationsbox.
2.	Starten Sie den MAGELLAN-Importformat Converter über den Explorer. Rufen Sie dazu die Datei MagellanIFConv.exe im Programmordner von Magellan (z.B. C:\Stueber Software\MAGELLAN 6\MagellanIFConv.exe).
3.	Seite **Anwendung** – In der Auswahlbox für das Programm müssen Sie ```IBIS``` auswählen.
4.	Seite **Quelle/Ziel** – Geben Sie in das obere Feld den Pfad an, in dem die IBIS-FoxPro Datenbanken (.DBF) liegen. 
5.	Seite **Quelle/Ziel** – Geben Sie in das untere Feld den Pfad an, in dem die konvertierten MAGELLAN-Importformat Dateien abgespeichert werden sollen.
6.	Seite **Der Assistent ist bereit **– Klicken Sie auf ```Fertigstellen```, um die Konvertierung zu starten. Nach der Konvertierung liegen Die MAGELLAN-Importformatdateien im .CSV-Format in dem von Ihnen angegebenen Dateipfad.

>ACHTUNG<br/>Grundsätzlich liegen zwei von den zu importierenden Datenbanken in IBIS verschlüsselt vor und müssen entschlüsselt werden. Bei der Entschlüsselung in IBIS werden die Datenbanken in den von uns abgefragten Dateien im IBIS-Datenbankordner abgelegt.

Verschlüsselt	|Unverschlüsselt
--|--
IBISEBS.DBF|	IBISEKEY.DBF 
KAR3PLUS.DBF	|	KAR3PKEY.DBF

Bevor Sie die Daten konvertieren, entschlüsseln Sie bitte die Datenbanken in IBIS wie folgt.
1.	Melden Sie sich als IBIS-Administrator an
2.	Wechseln Sie in das Menü ```TOOLS|DATEN ENT- UND VERSCHLÜSSELN```
3.	Die Schaltfläche ```Datenbank entschlüsseln``` muss aktiviert sein.
4.	Markieren Sie die gewünschte Datei und klicken Sie auf ```WEITER```.
5.	Die Datei wird von IBIS unverschlüsselt abgelegt. Wiederholen Sie den Vorgang für alle benötigten Datenbanken.

## Schritt 2: Konvertierte Daten korrigieren

### Fächer
Die IBIS-Datei FACHDEF.DBF enthält die Fachdefinitionen, darüber hinaus allerdings auch weitere Definitionen, bei denen es sich nicht um Fächer im eigentlichen Sinne handelt. Da bei der Konvertierung nicht gut unterschieden werden kann, sollten Sie sich die konvertierte Datei```BS_Fächer.keys``` in einem Texteditor oder mit Excel ansehen und ggf. Datensätze die keine Fächer enthalten entfernen. 

### Noten
Das Schlüsselverzeichnis der ```Noten``` in Magellan besteht aus den Noten 1-6 und den Punkten 1-15, sowie zwei Füllwerten „-“ für durchgestrichen und „ab“ für abgewählt. Diese Werte werden bei der Konvertierung und für den Import erkannt.<br/>
Wenn die letzten beiden Stellen der IBIS-Note Zahlen enthalten, dann entnehmen wir diese und setzen sie als Noten oder Punkte in Magellan ein, z.B. Gm 05 wird zu Note 5. Wenn sich aber in IBIS Füllwerte befinden wie z,B. #,##, oder andere Werte, in denen sich keine Zahlenwerte befinden, dann belassen wir diese Felder so wie sie sind.<br/> 
Wenn Sie diese Werte nicht benötigen oder etwas Sinnvolleres in Magellan daraus machen möchten, dann können Sie diese Werte bereits zu diesem Zeitpunkt in der CSV-Datei mit Excel korrigieren oder sie mit Beschreibung im Noten-Schlüsselverzeichnis eintragen.

### Betriebe und Sorgeberechtigte
Während der Testphase haben wir festgestellt, dass viele Betriebe und Sorgeberechtigte in IBIS mehrfach erfasst wurden. Nach der Konvertierung in die Datei Magellan-Importformatdatei hätten Sie die Gelegenheit die Datei in Excel zu laden und entsprechend Ihrer Vorgaben zu sortieren und damit mehrfache Eintragungen zu finden und ggf. zu korrigieren bzw. zusammenzufassen, bevor diese nach Magellan importiert werden. <br/>
Wichtig ist, dass Sie keine Änderungen an den Primärschlüsseln machen, da diese benötigt werden, um die Entsprechungen für Schüler-Ausbildung bzw. Schüler-Sorgeberechtigte zu finden. Änderungen an diesen Feldern, setzen voraus, dass Sie auch die Dateien schueler_sorgebe.import.csv und schueler_ausbildung.import.csv entsprechend Ihrer Änderung anpassen. 
Beispiel doppelte Sorgeberechtigte in IBIS:<br/>
* Claudia Musterfrau 	Hansstraße 3
* Klaudia Musterfrau	  	Hansstr.3

Korrektur für die Importdatei: Sie entfernen z.B. den zweiten Datensatz und behalten den ersten (Claudia Musterfrau Hansstraße 3)<br/>
In der Importdatei schueler_sorgeberechtigte.import.csv befinden sich zwei Kinder dieser Frau, die bei Ihnen als Schüler eingetragen sind:
* Peter Musterfrau…. Eintrag beim Sorgeberechtigten: Claudia Musterfrau
* Hanne Musterfrau…. Eintrag beim Sorgeberechtigten: Klaudia Musterfrau

Sie müssten dann an dieser Stelle Klaudia Musterfrau in Claudia Musterfrau ändern.

## Schritt 3: Manuelle Anpassungen

Aufgrund der Besonderheit, dass in IBIS die Datenbank frei erweitert und verändert werden kann, halten Sie ggf. weitere Informationen, die Sie evtl. nach Magellan importieren können. An dieser Stelle haben Sie die Möglichkeit die Dateien vor dem Import in Excel zu bearbeiten und ggf. zusätzliche Spalten und Daten manuell bzw. per Kopieren und Einfügen aus der Quelldatei einzufügen. Welche Datenfelder im Magellan-Importformat möglich sind und wie Sie diese importieren können, lesen Sie bitte im Kapitel Magellan-Importformat.
Nachfolgend finden Sie dazu ein Beispiel anhand der Schülerdaten.
1.	Öffnen Sie die IBIS-FoxPro Datenbank, in der sich weitere zu importierende Datenfelder befinden, mit Microsoft Excel,
Beispiel: IBISEKEY.DBF
2.	Öffnen Sie die dazu passende Importformatdatei, die Sie zuvor mit dem MAGELLAN-Importformatkonverter erstellt haben, in Microsoft Excel, Beispiel: schueler.import.csv
3.	Markieren Sie in der IBISEKEY.DBF die gesamte Spalte mit Inhalt, die zusätzlich nach Magellan importiert werden soll und kopieren Sie diese in den Speicher (Tastenkombination ```Strg+C``` ), Beispiel: Eine Spalte mit dem Namen **GEBORT** für Geburtsort des Schülers
4.	Wechseln Sie zur geöffneten schueler.import.csv und kopieren Sie die Spalte dort an das Ende ( Tastenkombination ```Strg+V``` )
5.	Ändern Sie den Spaltennamen entsprechenden dem MAGELLAN-Importformat und speichern Sie die schueler.import.csv, Beispiel: Ändern Sie die Benennung der Spalte mit dem Namen **GEBORT** in **Geburtsort** um, dies entspricht der Beschreibung des Importformates.Der Importmechanismus im Magellan-Administrator würde eine Spalte Geburtsort erkennen und diese nach MAGELLAN importieren.


## Schritt 4: Vorbereiten der MAGELLAN-Datenbank

Nach erfolgreicher Konvertierung sollte die MAGELLAN-Datenbank für den Import vorbereitet werden.

### MAGELLAN-Datenbank leeren
Üblicherweise liefert STÜBER SYSTEMS eine Datenbank mit Beispielinhalten. Diese Daten müssen vor dem Import gelöscht werden. Dazu gehen Sie bitte wie folgt vor.
1.	Starten Sie den MAGELLAN-Administrator. 
2.	Wählen Sie die Ansicht ```Datenbankpflege``` und führen Sie ```Datenbankinhalt löschen``` aus.
3.	Markieren Sie den Haken bei ```Postleitzahlverzeichnis beibehalten``` 

### Zeiträume anlegen
Erstellen Sie alle in MAGELLAN notwendigen Zeiträume über ```Verzeichnisse | Zeiträume```. Die notwendigen Zeiträume erkennen Sie anhand des niedrigsten und höchsten Schuljahres in der schueler_laufbahn.csv bzw. anhand ihrer Schuljahre in IBIS. Für MAGELLAN wird pro Schuljahr ein Halbjahresdatensatz benötigt, Beispiel:
1. Halbjahr 2010/2011 – Von: 01.08.2010 Bis: 31.01.2011
2. Halbjahr 2011/2011 – Von: 01.02.2011 Bis: 31.07.2011
Diese genauen Datumsangaben sind für den Import vorgesehen und müssen eingetragen werden!

### Fächer-Schlüssel kopieren
Nach der Konvertierung der Daten haben Sie ggf. die Datei BS_Faecher.keys. Diese muss in den ```Magellan \Importe\Nordrhein-Westfalen``` Ordner kopiert werden und enthält die Fächer aus IBIS.

### Schlüsselverzeichnisse importieren
Importieren Sie die in MAGELLAN mitgelieferten Schlüsselverzeichnisse für Nordrhein-Westfalen nach Magellan. Gehen Sie dabei wie folgt vor.
1.	Starten Sie den MAGELLAN-Administrator. 
2.	Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Schlüsselverzeichnisse importieren``` aus.
3.	Geben Sie als Parameter ihr ```Bundesland```, Ihre ```Schulart```, den ```Mandanten``` und ```Alle Kataloge``` an.

### Schuldaten importieren
Aufgrund ihrer allgemeingültigen Form in Nordrhein-Westfalen können Schuldaten direkt, ohne Konvertierung, nach MAGELLAN importiert werden. Dies ist möglich, da das Ministerium entsprechend eine Liste aller aktuellen Schulen im Bundesland zur Verfügung stellt. Der Import der Schulen erfolgt ebenfalls über das allgemeine MAGELLAN-Importformat. 
Wir stellen Ihnen zwei mögliche Schulimportdateien bereit. Eine Gesamtschulliste und eine ohne Grundschulen. Die Importdateien der Schulen befinden sich im Datenunterordner ```\Importe\Nordrhein-Westfalen```. Kopieren Sie die für Sie passende Importdatei in das Verzeichnis mit den konvertierten IBIS-Daten und benennen Sie die Datei in ```schulen.import.csv``` um.

> #### primary::Hinweis
>
> Sollten Schulen fehlen, können Sie die Importdatei in Excel öffnen und weitere Schulen für den Import eintragen.


## Schritt 5: Import der Daten nach MAGELLAN

Nach erfolgreicher Vorbereitung der Datenbank kann die Zieldatei über den MAGELLAN-Administrator importiert werden.
1.	Starten Sie den MAGELLAN-Administrator. 
2.	Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Daten über MAGELLAN-Importformat importieren``` aus.
3.	Lesen Sie bitte im Kapitel „MAGELLAN-Importformat“ , wie Sie die Daten korrekt nach MAGELLAN importieren.

## Schritt 6: Bereinigen von Importartefakten

Durch die Konvertierung der IBIS-Daten entstehen Nebeneffekte, die sich während des Konvertierungs- oder Importprozesses nicht vermeiden oder schlecht korrigieren lassen. Aus diesem Grund müssen nach dem Import weitere Korrekturen vorgenommen werden.<br/>

Die Korrektur dieser Artefakte erfolgt in der Ansicht ```Datenbankpflege``` des MAGELLAN-Administrator unter dem Punkt``` Datenbank überprüfen```.
![](sshot-7.png)

### Klassenzeiträume korrigieren
Bei der Konvertierung der Klassen werden die Zeiträume in denen die Klassen existieren größtmöglich bemessen, dadurch existieren die Klassen auch in Zeiträumen, in denen es keine Schüler gibt. Dies wird korrigiert, wenn Sie unter``` Was möchten Sie tun?``` die Option ```Klassenzeiträume korrigieren``` auswählen.

### Unterstriche in Schülernamen entfernen
In IBIS war es üblich Schülerdaten zu kopieren, wenn Sie in einen weiteren Bildungsgang anfingen. Zur Unterscheidung dieser Schüler wurde mangels einer ID als Primärschlüssel der Name genutzt. Die kopierten Schüler erhielten Unterstriche im Vornamen. Die Konvertierung und der Import nehmen sich dieser doppelten Schüler an und verpassen den Schülern eine Interne ID, wenn der Schüler eigentlich bereits importiert wurde. Damit kann sich die Laufbahn rekonstruieren lassen. Diese Korrektur nimmt sich dann noch zusätzlich den Unterstrichen an und entfernt diese restlos, wenn Sie unter ```Was möchten Sie tun?``` die Option ```Unterstriche in Schülernamen entfernen ```auswählen.

## Übersicht der unterstützten IBIS Dateien und Importfelder

In der nachfolgend aufgelisteten Tabelle erhalten Sie eine Übersicht der Daten, die für den Import von IBIS nach MAGELLAN über das allgemeine Importformat und dem Importformatkonverter bereits unterstützt werden. Ausgenommen sind zusätzliche Felder, die Sie evtl. manuell in die Importdateien hinzufügen, wie in Schritt 2: ```Konvertierte Daten korrigieren``` beschrieben.
Für die Konvertierung/Import benötigte Pflichtfelder werden hervorgehoben dargestellt.

### FACHDEF.DBF
In der FACHDEF.DBF Datei befinden sich die Fachdefinitionen. Fächer sind in Magellan Schlüsselver-zeichnisse und werden nach der Konvertierung mit dem Magellan-Administrator über die Funktion ```Import von Schlüsselverzeichnissen``` nach MAGELLAN importiert. 

Feld in der Tabelle	|Bedeutung
--|--
FACHKURZ	|Kürzel des Fachs
FACHNAME	|Bezeichnung des Fachs
FACHFAKTOR|	Faktor des Fachs

>HINWEIS<br/>
Üblicherweise werden Schlüsselverzeichnisse vom Bildungsministerium oder dem Landesstatistikamt zur Verfügung gestellt. Für Nordrhein-Westfalen existieren derzeit keine Fächerschlüssel. Deshalb entneh-men wir diese aus den IBIS-Daten.

### FIRMEN.DBF
In der FIRMEN.DBF Datei befinden sich die Betriebedaten.

Feld in der Tabelle	|Bedeutung
--|--
NAMEBETRIEB	|Name 1 des Betriebes
NAME2BETRIE|	Name 2 des Betriebes
STRBETRIEB	|Straße des Betriebes
PLZBETRIEB	|PLZ des Betriebes
ORTBETRIEB	|Ort des Betriebes
TELBETRIEB	|Telefon des Betriebes
FAXBETRIEB	|Telefax des Betriebes
EMAILBETRIEB	|Email-Adresse des Betriebes
FIRMBEMERK	|Anmerkungen zum Betrieb
KAMMER	|Angehörige Kammer des Betriebs

### IBISEKEY.DBF
In der IBISEKEY.DBF Datei befinden sich die Daten der Schüler, Sorgeberechtigten, 
Schueler-Ausbildung, Schueler-Sorgeberechtigten und Schueler-Schulen. 

Feld in der Tabelle	|Bedeutung
--|--
SCHUELERNA	|Nachname des Schülers
VORNAMESCH	|Vorname des Schülers
ANREDE1SCH	|Anrede des Schülers
GESCHLECHT	|Geschlecht des Schülers
GEBDAT	|Geburtsdatum des Schülers
GEBORT|	Geburtsort des Schülers
STRASSE	|Straße des Schülers
PLZ	|PLZ des Schülers
WOHNORT|	Wohnort des Schülers
TELEFON	|Telefon des Schülers
EMAILSCH	|Email-Adresse des Schülers
STAATSANGE	|Staatsangehörigkeit 1 des Schülers
MUTTERSPRA	|Muttersprache des Schülers
KONFESSION|	Konfession des Schülers
RELAB	|Abmeldung vom Religionsunterricht Von
RELAB|	Abmeldung vom Religionsunterricht Bis
FAHRKARTEN	|Fahrkarten Merkmal des Schülers
SPAETAUSSI	|Aussiedlerstatus des Schülers
ZUZUGSJAHR	|In Deutschland seit Datum des Schülers
BAFOEG	|Bafög Merkmal des Schülers
FOERDERSCH	|Förderschwerpunkt des Schülers
SPRACHE1	|1. Fremdsprache des Schülers
SPRACHE2	|2. Fremdsprache des Schülers
SPRACHE3	|3. Fremdsprache des Schülers
DAUSPRA1	|1. Fremdsprache seit Klassenstufe
DAUSPRA2	|2. Fremdsprache seit Klassenstufe
DAUSPRA3	|3. Fremdsprache seit Klassenstufe
BISSPRA1|1. Fremdsprache bis Klassenstufe
BISSPRA2	|2. Fremdsprache bis Klassenstufe
BISSPRA3	|3. Fremdsprache bis Klassenstufe
EINSCHULUN	|Grundschuleintritt des Schülers
QUALSCHULE	|Höchster Allgemeinbildender Abschluss des Schülers
QUALBERUF	|Höchster berufsbildender Abschluss des Schülers
TRAEGER	|Statistikmerkmal TRAEGER der Landesstatistik
BKAZVO|	Statistikmerkmal BKAZVO der Landesstatistik
WAHL1	|Wahlfach 1 des Schülers
WAHL2	|Wahlfach 2 des Schülers
WAHL3	|Wahlfach 3 des Schülers
WAHL4|	Wahlfach 4 des Schülers
VORNAMEERZ	|Vorname des 1. Sorgeberechtigten
FAMILIENNA|	Nachname des 1. Sorgeberechtigten
ANREDE1ERZ	|Anrede des 1. Sorgeberechtigten
STRASSEERZ	|Straße des 1. Sorgeberechtigten
PLZERZ	|PLZ des 1. Sorgeberechtigten
WOHNORTERZ	|Wohnort des 1. Sorgeberechtigten
TELEFONERZ	|Telefon Privat des 1. Sorgeberechtigten
TELEDIENST|	Telefon Beruflich des 1. Sorgeberechtigten 
EMAIL	|E-Mail-Adresse des 1. Sorgeberechtigten
GEBLANDERZ|	Geburtsland des 1. Sorgeberechtigten
ART	|Verhältnis zwischen Schüler und 1. Sorgeberechtigten, z.B. Vater, Mutter, etc.
VORNERZ2	|Vorname des 2. Sorgeberechtigten
NAMEERZ2	|Nachname des 2. Sorgeberechtigten
TITELER2	|Anrede des 2. Sorgeberechtigten
STRERZ2	|Straße des 2. Sorgeberechtigten
PLZERZ2	|PLZ des 2. Sorgeberechtigten
ORTERZ2	|Wohnort des 2. Sorgeberechtigten
TELERZ2	|Telefon Privat des 2. Sorgeberechtigten
TELEDIENER2	|Telefon Beruflich des 2. Sorgeberechtigten
GEBLANDER2	|Geburtsland des 2. Sorgeberechtigten
SCHULNR	|Schulnummer der Herkunftsschule
SCHULFORML	|Schulform der Herkunftsschule
ENTLASSENA	|Letzte Klasse der Herkunftsschule
NAMEBETRIE	|Name des Ausbildungsbetriebes
AUSBIBERUF	|Beruf des Schülers
VERTRAGSBE	|Ausbildung von des Schülers
VORAUSENDE	|Ausbildung bis des Schülers
FIRMBEMERK	|Anmerkungen zur Ausbildung
AUSBILDLEI	|Ausbildungskontakt des Schülers
ANLAGE	|Eintritt in die Schulform
EINTRITTKL	|Eintritt in die Klasse
GUID	|Externe GUID

### KAR3PKEY.DBF
In der KAR3PKEY.DBF Datei befinden sich die Laufbahn- und Fachdaten des Schülers. Sehr wichtig ist die korrekte und vollständige Angabe der Klassen und der Eintritts- und Austrittsdaten, da ansonsten keine oder nur eine fehlerhafte Zuordnung in die MAGELLAN Zeiträume und Laufbahnen erstellt werden kann.

Feld in der Tabelle|	Bedeutung
--|--
SCHUELERNA	|Nachname des Schülers
VORNAMESCH	|Vorname des Schülers
GESCHLECHT|	Geschlecht des Schülers
Bemerkung 7	|Fachdaten des Schülers
Bemerkung 8|	Abitur-Fachdaten des Schülers
Klasse1-Klasse13	|Entsprechende Klasse des Schülers
Eintritt1-Eintritt13|	Eintrittsdatum in die entsprechende Klasse
Austritt1-Austritt13|	Austrittsdatum aus der entsprechenden Klasse

### KLASSEDE.DBF
In der KLASSEDE.DBF Datei befinden sich die Klassendaten und, wenn die LEHRER.DBF nicht gepflegt wurde, werden hier die Lehrerkürzel aus dem Feld LEHRERSTAT entnommen.

Feld in der Tabelle|	Bedeutung
--|--
KLASSEJETZ	|Kürzel der Klasse
KLASSEKURZ	|Statistikkürzel der Klasse
OBERSTUFE|	Klassenart der Klasse
PUNKTE|	Notenart der Klasse
ORGFORM	|Organisation der Klasse
KLASSESTAT	|Bildungsgang der Klasse
FOERDERSCH	|Förderschwerpunkt der Klasse
LEHRERSTAT	|Klassenlehrer / Kürzel des Lehrers
KLASSESTUF	|Klassenstufe der Klasse
JVA	|Statistikmerkmal JVA der Landesstatistik
KLASSLEHRER	|Nachname des Klassenlehrers
KLASLHERGS	|Geschlecht des Klassenlehrers

### LEHRER.DBF
In der LEHRER.DBF Datei befinden sich die Lehrerdaten. Wenn diese Datei nicht gepflegt wurde, dann können keine Lehrerstammdaten übernommen werden. Lediglich das Lehrerkürzel kann aus der KLASSEDE.DBF entnommen werden.

Feld in der Tabelle|	Bedeutung
--|--
LEHRERSTAT|	Kürzel des Lehrers
LVORNAME	|Vorname des Lehrers
LNAME	|Nachname des Lehrers
GESCHLECHT|	Geschlecht des Lehrers
PERSONALNR|	Personalnummer des Lehrers
LGEBDAT	|Geburtsdatum des Lehrers
LSTRASSE	|Straße des Lehrers
LPLZ	|Postleitzahl des Lehrers
LWOHNORT	|Wohnort des Lehrers
LTELEFON	|Telefonnummer des Lehrers
LTELEFAX	|Telefaxnummer des Lehrers
LHANDY	|Mobilnummer des Lehrers
LEMAIL	|Email-Adresse des Lehrers
PKW1	|KFZ-Kennzeichen 1
PKW2	|KFZ-Kennzeichen 2
STAATSANGE	|Staatsangehörigkeit des Lehrers
KONFESSION	|Konfession des Lehrers
EINTRITT	|Zugangsdatum des Lehrers
AUSTRITT	|Abgangsdatum des Lehrers
AMTSBEZ	|Amtsbezeichnung des Lehrers
ANMERKUNG1	|Anmerkungen zum Lehrer
