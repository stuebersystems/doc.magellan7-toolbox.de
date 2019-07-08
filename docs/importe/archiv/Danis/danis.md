# Danis

Die Datenübernahme aus dem Schulverwaltungsprogramm DANIS ermöglicht den Import von Sorgebe-rechtigte-,  Schüler- (inkl. Verbindung Schüler-Sorgeberechtige), Schülerlaufbahnen, Klassen- und Lehrerdaten nach MAGELLAN. Die DANIS MySQL-Datenbank kann über den MAGELLAN-Importformat Konverter ausgelesen und in das MAGELLAN-Importformat konvertiert werden. 
Der Import erfolgt in drei Schritten:
1.	Konvertieren in das MAGELLAN-Importformat
2.	Vorbereiten der MAGELLAN-Datenbank
3.	Import der Daten nach MAGELLAN

## Übersicht der Importdateien die aus den DANIS Daten erzeugt werden

Die DANIS Datenbank ist relational aufgebaut und enthält viele Verweise auf andere Tabellen. Um an die entsprechenden Daten für den Import zu gelangen wird immer eine Abfrage über viele Tabellen benötigt. Die in der Tabelle genannte DANIS-Tabelle ist somit immer nur der Einstiegspunkt zu den entsprechenden Daten.

| Importdatei | DANIS-TABELLE | Beschreibung|
| -- | -- | -- |
| lehrer.import.csv | lehrer  | Enthält die Stammdaten der Lehrer |
| sorgebe.import.csv | verantwortlicher |enthält die Stammdaten der Sorgeberechtigten |
| klassen.import.csv | gruppe | Enthält die Stamm- und Zeitraumdaten der Klassen. <br>Bedingung: Vorhandensein der Zeiträume in Magellan.|
| schueler.import.csv | schueler | Enthält die Stammdaten der Schüler und Bewerber |
| schueler_laufbahn.import.csv |jahrgangsdaten | Enthält die Laufbahndaten der Schüler. Es werden nur Laufbahnen bis Klassenstufe 10 berücksichtigt.<br>
Weitere Bedingung: Import der klassen.import.csv |
| schueler_sorgebe.import.csv |schuelerverant-wortlicher | Enthält die Zuordnung der Sorgeberechtigten zu den Schülern<br>Weitere Bedingung: Import der sorgebe.import.csv |

## Schritt 1: Konvertieren in das MAGELLAN-Importformat

Navigieren Sie im Importformat Konverter über die Schalflächen „Zurück“ und „Weiter“, um zu den entsprechenden Seiten des Assistenten zu gelangen. Wenn Sie die Konvertierung starten, werden zuerst die Spaltennamen und die Pflichtfelder überprüft. Treten keine Probleme auf, werden die Quelldaten in die Zieldateien übernommen.

1.	Starten Sie den MAGELLAN-Importformat Converter über den Explorer. Rufen Sie dazu die Datei MagellanIFConv.exe im Programmordner von MAGELLAN (z.B. ```C:\Stueber Software\Magellan 6\MagellanIFConv.exe```).
2.	Seite **Anwendung** – In der Auswahlbox für das Programm müssen Sie ```DANIS``` auswählen.
3.	Seite **Quelle/Zie**l – Geben Sie in das obere Feld den Pfad zur Datei libmysql.dll an. Diese Datei wird bei der Installation von Danis mit in den Installationsunterordner \Server\bin gelegt. 
4.	Seite **Quelle/Ziel** – Geben Sie in das nächste Feld  das Kennwort des MySQL Root-Benutzers ein.
5.	Seite **Quelle/Ziel** – Wenn Sie das Kennwort korrekt eingegeben haben und Zugriff auf die MySQL Datenbank problemfrei erfolgen konnte (passiert im Hintergrund), dann können Sie im nachfolgenden Feld Ihre Danis Datenbank aus der Combobox auswählen.
6.	Seite **Quelle/Ziel** – Zuletzt geben Sie den Pfad an, in den die konvertierten MAGELLAN-Importformat Dateien gespeichert werden sollen.
7.	Seite **Der Assistent ist bereit** – Klicken Sie auf ```Fertigstellen```, um die Konvertierung zu starten. Nach der Konvertierung liegen die MAGELLAN-Importformatdateien im .CSV-Format in dem von Ihnen angegebenen Dateipfad.


## Schritt 2: Vorbereiten der Magellan-Datenbank

Nach erfolgreicher Konvertierung sollte die MAGELLAN-Datenbank für den Import vorbereitet werden.

### Magellan-Datenbank leeren
Üblicherweise liefert STÜBER SYSTEMS eine Datenbank mit Beispielinhalten. Diese Daten müssen vor dem Import gelöscht werden. Dazu gehen Sie bitte wie folgt vor.
1.	Starten Sie den MAGELLAN-Administrator. 
2.	Wählen Sie die Ansicht ```Datenbankpflege``` und führen Sie ```Datenbankinhalt löschen``` aus.
3.	Markieren Sie den Haken bei ```Postleitzahlverzeichnis beibehalten``` 

### Zeiträume anlegen
Erstellen Sie alle in MAGELLAN notwendigen Zeiträume über ```Verzeichnisse > Zeiträume```. Die notwendigen Zeiträume erkennen Sie anhand des niedrigsten und höchsten Schuljahres in der schueler_laufbahn.import.csv bzw. anhand ihrer Schuljahre in DANIS. Für MAGELLAN wird pro Schuljahr ein Halbjahresdatensatz benötigt, Beispiel:
4. Halbjahr 2010/2011 – Von: 01.08.2010 Bis: 31.01.2011
5. Halbjahr 2011/2011 – Von: 01.02.2011 Bis: 31.07.2011
Diese genauen Datumsangaben sind für den Import vorgesehen und müssen eingetragen werden!

##Schlüsselverzeichnisse importieren
Importieren Sie die in MAGELLAN mitgelieferten Schlüsselverzeichnisse für Niedersachsen nach Magellan. Gehen Sie dabei wie folgt vor.
6.	Starten Sie den MAGELLAN-Administrator. 
7.	Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Schlüsselverzeichnisse importieren``` aus.
8.	Geben Sie als Parameter ihr ```Bundesland```, Ihre Schulart, den ```Mandanten``` und ```Alle Kataloge``` an.

## Schritt 3: Import der Daten nach MAGELLAN

Nach erfolgreicher Vorbereitung der Datenbank kann die Zieldatei über den MAGELLAN-Administrator importiert werden.
1.	Starten Sie den MAGELLAN-Administrator. 
2.	Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Daten über MAGELLAN-Importformat importieren``` aus.
3.	Lesen Sie bitte im Kapitel „MAGELLAN-Importformat“ , wie Sie die Daten korrekt nach MAGELLAN importieren.


## Übersicht der unterstützten DANIS Importfelder

In der nachfolgend aufgelisteten Tabelle erhalten Sie eine Übersicht der Daten, die für den Import von DANIS nach MAGELLAN über das allgemeine Importformat und dem Importformat Konverter bereits unterstützt werden. Ausgenommen sind zusätzliche Felder, die Sie evtl. manuell in die Importdateien hinzufügen.

Für die Konvertierung/Import benötigte Pflichtfelder werden hervorgehoben dargestellt.

### lehrer.import.csv
| Feld in der Importdatei | Feld in Danis | Tabelle in Danis |
| -- | -- | -- |
| Kuerzel | Kuerzel2 | Lehrer|
| Vorname | Vornamen, Rufname| Person |
| Nachname | Nachname| Person |
| Geschlecht | Geschlecht | Person |
| Geburtsdatum |Geburtsdatum| Person |
| Geburtsort | Geburtsort| Person |
| Strasse | Strasse | Adresse |
| PLZ | PLZ | Ort |
| Ort | Name | Ort |
| Ortsteil | Ortsteil | Ort |
| Telefon |Adresse (0) | Kontakt|
|Telefax | Adresse (3) |Kontakt |
| Email | Adresse (1) | Kontakt |
| Staatsangeh | Kennzahl | Land |
| Konfession| Kennzahl | Konfession |
|Personalnr | Personalnummer| Lehrer |
| ZugangDatum | Zugang | Lehrer |
| ZugangGrund |Grund| Lehrer |
| AbgangDatum | Abgang| Lehrer |
| AbgangGrund | Grund | Lehrer |
| Dienstbez | Kennzahl | Dienstbezeichnung |
| Bemerkung | Bemerkungen |Lehrer |


### sorgebe.import.csv
| Feld in der Importdatei | Feld in Danis | Tabelle in Danis|
| -- | -- | -- |
| Vorname | Vornamen, Rufname |Person |
| Nachname| Nachname| Person|
| Strasse | Strasse| Adresse |
| PLZ| PLZ | Ort |
| Ort | Name | Ort |
| Ortsteil | Ortsteil | Ort |
| TelefonPrivat | Adresse (0)|Kontakt |
| Email |Adresse (1 | Kontakt |

### klassen.import.csv

|Feld in der Importdatei	|Feld in Danis	|Tabelle in Danis|
|--|--|--|
|Kuerzel|	Bezeichnung	|Gruppe|
|ZeitraumVon|	Bezeichnung	|Schuljahre|
|ZeitraumBis	|Bezeichnung	|Schuljahre|
|Halbjahr|	Bezeichnung|	Schuljahre|
|Schulform|	Kennzahl|	Schulform|
|Integration|	Integrationsklasse|	Gruppe|
|Klassenleiter1Kuerzel|	Kuerzel|	Lehrer|
|Klassenleiter2Kuerzel|	Kuerzel	|Lehrer|
|Klassenstufe|	Jahrgangsstufe|	Gruppe|


### schueler.import.csv

|Feld in der Importdatei	|Feld in Danis|	Tabelle in Danis
|--|--|--|
|Vorname	|Vornamen, Rufname	|Person|
|Nachname|	Nachname	|Person|
|Geburtsdatum|Geburtsdatum	|Person|
|Anrede|	Titel	|Person|
|Geschlecht|	Geschlecht|	Person|
|Geburtsort|	Geburtsort|	Person|
|Geburtsland|	Kennzahl|	Land|
|Strasse	|Strasse|	Adresse|
|PLZ	|PLZ|	Ort|
|Ort	|Name|	Ort|
|Ortsteil	|Ortsteil	|Ort|
|Telefon	|Adresse (0)|	Kontakt|
|Telefax	|Adresse (3)|	Kontakt|
|Email	|Adresse (1)|	Kontakt|
|Staatsangeh1	|Kennzahl	|Land|
|Verkehrssprache|	Kennzahl|	Sprache|
|Konfession	|Kennzahl	|Konfession|
|Krankenkasse|Bezeichnung|	Krankenkasse|
|Fahrschueler|	Fahrschueler|	Schueler|
|InDeutschlandSeit|	Zuzugsjahr	|Schueler|
|Grundschuleintritt	|ErstEinschulJahr|	Schueler|
|ZugangAm	|Aufnahmedatum|	Schueler|
|AbgangAm	|Abgangsdatum|Schueler|
|Bemerkung|Bemerkungen|	Schueler|


### schueler_sorgebe.import.csv

|Feld in der Importdatei	Feld in Danis	Tabelle in Danis|
|--|--|--|
|SchuelerVorname|	Vornamen, Rufname	|Person|
|SchuelerNachname|Nachname	|Person|
|SchuelerGeburtsdatum|Geburtsdatum|	Person|
|SorgebeVorname|Vorname	|Person|
|SorgebeNachname|	Nachname|	Person|
|SorgebeStrasse	|Strasse|	Adresse|
|SorgebeOrt|	Name|	Ort|
|Verhaeltnis	|Art|	Verantwortlicher|

### schueler_laufbahn.import.csv

|Feld in der Importdatei	Feld in Danis	Tabelle in Danis|
|--|--|--|
|SchuelerVorname|	Vornamen, Rufname|	Person|
|SchuelerNachname	|Nachname|	Person|
|SchuelerGeburtsdatum|Geburtsdatum|	Person|
|KlasseKuerzel|Bezeichnung	|Gruppe|
|ZeitraumVon	|Bezeichnung	|Schuljahr|
|ZeitraumBis	|Bezeichnung|Schuljahr|
|Halbjahr	|Bezeichnung|	Schuljahr|
|Gewechselt	|Status	|Jahrgangsdaten|
|Wiederholer	|Status (6)|	Jahrgangsdaten|
|Ueberspringer|Status (2)|	Jahrgangsdaten|
|Versetzt	|Status (1,2,3)|	Jahrgangsdaten|
|Abschluss1	|Kennzahl	|Abschlussart|



