# LUSD (Hessen)

Die Datenübernahme aus den Schulverwaltungsprogramm LUSD in Hessen erfolgt auf Basis der Exportschnittstelle in LUSD zum Programm Littera, die den Export von Schülerstammdaten ermöglicht. Der Import erfolgt in drei Schritten:
1.	Export der Daten aus LUSD.
2.	Konvertieren der Textdatei in das MAGELLAN-Importformat über den MAGELLAN-Importformatkonverter.  (z.B. C:\Stueber Software\Magellan 6\MagellanIFConv.exe).
3.	Import der Dateien im MAGELLAN-Importformat nach MAGELLAN.

## Schritt 1: Export der Daten aus LUSD

Zum Export der Schülerstammdaten gehen Sie in LUSD wie folgt vor:
1.	Rufen Sie ```Dienste|Ex-Import``` auf.
2.	Gehen Sie auf Littera-Windows und erstellen Sie eine MDB-Datei.
3.	Öffnen Sie die erstellte MDB mit Access.
4.	In Access markieren Sie die Tabelle Schueler und starten Sie mit der rechten Maustaste das Kontextmenü. Klicken Sie dort auf ```Exportieren```.
5.	Im darauf folgenden Menü müssen Sie angeben, dass die Datei unter den Dateityp Textdateien(*.txt;*.csv;*.tab;*.asc;)  gespeichert werden soll.
6.	Im Assistenten müssen Sie Mit Trennzeichen... einstellen und auf ```Weiter``` klicken.
7.	Dann das Trennzeichen auf Semikolon setzen und das Feld Feldnamen in erste Zeile einbeziehen aktiviert.

## Schritt 2: Konvertieren der Exportdatei in das MAGELLAN-Importformat

Die aus LUSD exportierte Datei muss jetzt in das MAGELLAN-Importformat für Schülerdaten gebracht werden. Dies erfolgt über den MAGELLAN-Importformatkonverter. Voraussetzung hierfür ist eine Installation von Excel auf dem Rechner.
1.	Starten Sie den Magellan-Importformat Converter über den Explorer. Rufen Sie dazu die Datei MagellanIFConv.exe im Programmordner von MAGELLAN (z.B. C:\Stueber Software\Magellan 6\MagellanIFConv.exe).
2.	Wählen Sie unter Programm wählen die Option LUSD aus. Klicken Sie dann auf ```Weiter```.
3.	Wählen Sie für die Quelldatei den Konvertierungstyp Schüler und die zuvor aus LUSD exportierte Datei aus. Klicken Sie auf ```Weiter```.
4.	Geben Sie den gewünschten Namen der Zieldatei an und klicken Sie auf ```Weiter```.
5.	Klicken Sie auf ```Starten```, um die Konvertierung zu starten.

## Schritt 3: Schülerdaten nach MAGELLAN importieren

Die im 2. Schritt erzeugte Datei entspricht jetzt dem MAGELLAN-Importformat für die Schülerdatei. Die Schülerdatei müssen Sie jetzt über den MAGELLAN-Administrator nach MAGELLAN importieren. Wie Sie dazu vorgehen müssen, erfahren Sie im Kapitel MAGELLAN-Importformat.

#' Importierte Felder

Folgende Felder werden aus dem aus LUSD exportierten Format in die Schülerdatei des MAGELLAN-Importformates übernommen:

|Nr.|Feldname bei LUSD-Exportdatei|Feldname im MAGELLAN-Importformat (Schülerdaten)|
|--|--|--|
|1|Vorname|Vorname|
|2|Nachname|Nachname|
|3|	Geschlecht	|Geschlecht|
|4	|Geburtsdatum|	Geburtsdatum|
|5|	Klasse|	Klasse|
|6|	Strasse|	Strasse|
|7	|Ort	|Ort|
|8|	PLZ	|PLZ|
|9	|Telefon|	Telefon|

