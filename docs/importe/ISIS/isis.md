# ISIS

Der Import der ISIS-Daten nach MAGELLAN erfolgt über die 32-Bit-ODBC-Schnittstelle von Microsoft. Über den ODBC-Treiber greift der MAGELLAN-Administrator direkt auf ISIS-Dateien im Verzeichnis DATEN von ISIS zu.

Beim Import der Daten aus ISIS werden alle zu importierenden Daten als neue Daten für MAGELLAN aufgefasst. 

Die nachfolgenden fünf Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm ISIS nach MAGELLAN.


## Schritt 1: Installation einer leeren Datenbank

Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:
1.	Rufen Sie den MAGELLAN-Administrator auf.
2.	Wählen Sie ```Ansicht``` und dann ```Datenbankpflege```. Wählen Sie die Option ```Datenbankinhalte löschen```.
3.	Klicken Sie auf ```OK```, um mit dem Erzeugen einer neuen Datenbank zu beginnen. 

>Achtung<br/>
Ihre bisherige Datenbank wird dabei gelöscht! Über die Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.

## Schritt 2: Mandanten und Zeitraum in MAGELLAN anlegen

In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Zeitraum und ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus ISIS werden in MAGELLAN zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Zeitraum und zu welchem Mandanten die Daten zugeordnet werden. Sinnvollerweise sollten in MAGELLAN je ein Zeitraum für das 1. und das 2. Halbjahr des aktuellen Schuljahres eingetragen werden. Zum Eintragen eines Zeitraums und eines Mandanten in MAGELLAN gehen Sie wie folgt vor:
1.	Rufen Sie ```MAGELLAN``` auf.
2.	Rufen Sie das Menü ```Verzeichnisse``` und dann den Menüpunkt ```Zeiträume``` auf.
3.	Fügen Sie im Dialogfenster Verzeichnis der Zeiträume die gewünschten Zeiträume ein.
4.	Tragen Sie unter Ansicht und dann Mandanten einen Mandanten ein. Die ist im Regelfall Ihre eigene Schule.
5.	Verlassen Sie MAGELLAN.


## Schritt 3: Statistikschlüssel und Postleitzahlen importieren

Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Statistikschlüssel und die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehal-ten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:
1.	Wählen Sie dazu Ansicht und dann Datenimporte. 
2.	Wählen Sie die Option Schlüsselverzeichnisse importieren.
3.	Wählen Sie anschließend die Option Postleitzahlverzeichnis importieren.

## Schritt 4: ISIS-Schlüssel an MAGELLAN-Schlüsselverzeichnisse anpassen

Zum Statistikabgleich erfolgt in ISIS die Zuordnung der verwendeten Bezeichner zu den Statistikschlüs-seln über das BADEMS-Programm. 
>Schlüssel	<br/>
Die Schlüssel im BADEMS-Programm müssen dabei den Schlüsselverzeichnissen in MAGELLAN entsprechen! Nur bei einer Übereinstimmung der jeweiligen Schlüssel können die Daten aus ISIS korrekt in Magellan eingelesen werden.

Die Standardeinstellungen der Schlüssel im BADEMS-Programm entsprechen dabei den Schlüsselver-zeichnissen in MAGELLAN, mit Ausnahme der Unterrichtsfächer. Hier muss eine manuelle Korrektur vorgenommen werden. Das nachfolgende Beispiel zeigt die Überprüfung und Korrektur des Schlüssels für das Fach „Erdkunde“.

Beispiel Schlüsselanpassung: Dem Fach "Erdkunde" wird im BADEMS-Programm standardmäßig der alte Schlüssel "20" zugeordnet. Der aktuelle Schlüssel für Erkunde ist "33" in der Schlüsseltabelle Fächer in Magellan. Zur Korrektur gehen Sie bitte wie folgt vor:

1.	Starten Sie ```MAGELLAN```.
2.	Rufen Sie das Menü ```Verzeichnisse``` und dann den Menüpunkt ```Fächer``` auf, um das Dialogfenster ```Verzeichnis der Fächer``` zu öffnen.
3.	Suchen Sie in der Spalte „Bezeichnung“ das Fach "Erdkunde". Sie finden den Eintrag "Erdkunde/Geographie/Wirtschaftgeogr". Notieren Sie in den zugehörigen Eintrag in der Spalte "Schlüssel" (=33).
4.	Verlassen Sie MAGELLAN und starten Sie das Programm BADEMS. Gehen Sie über ```Bearbeiten``` auf den Menüpunkt ```Unterrichtsfächer```. Suchen Sie in der Liste den Eintrag „Erdkunde“. Drücken Sie ```ESC```, um in den Editiermodus zu gelangen. Ändern Sie über den Befehl ```Ändern``` den Standardschlüssel von "20" auf "33". Drücken Sie Tastenkombination ```STRG+END```, um die Änderung zu speichern.

Sollten die Bezeichner in den Schlüsseltabellen von MAGELLAN nicht mit jenen in ISIS übereinstimmen, so können Sie die Bezeichner in MAGELLAN entweder vor oder auch nach dem Import durch Editieren Ihre gewohnten Bezeichner in ISIS anpassen.

## Schritt 5: ISIS-Daten importieren

Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der ISIS-Daten beginnen. Gehen Sie dazu wie folgt vor:
1.	Rufen Sie den ```MAGELLAN-Administrator``` auf.
2.	Wählen Sie Ansicht und dann ```Datenimporte```. Wählen Sie die Option ```Daten aus Verwaltungsprogrammen importieren```. Wählen Sie dabei im Auswahlfeld die Option ```ISIS (Rheinland-Pfalz)``` und klicken Sie dann auf ```Start```.
3.	Geben Sie im Dialogfenster ```Importiere ISIS``` den Ordner der ISIS-Daten an, wählen Sie einen Zeitraum, denen die aktuellen ISIS-Daten zugeordnet werden sollen (z.B. "1. Halbjahr 02/03" oder "2. Halbjahr 02/03"). Zusätzlich müssen Sie auch den Mandanten festlegen. Über die Option Umlaute umwandeln können Sie je nach Versionsausgabe von ISIS festlegen, ob die Umlaute umgewandelt werden sollen. Klicken Sie dann auf ```OK```.
4.	Der Import kann je nach Hardwarekonfiguration und Umfang Ihrer ISIS-Daten mehrere Minuten dauern. Nach Abschluss des Imports können Sie den MAGELLAN-Administrator wieder verlassen.

## Welche Daten werden übernommen?

### Ansicht Schüler
* Vorname, Name
* Klasse
* Geb.datum und -ort
* Geschlecht
* Straße, PLZ, Ort
* Telefon
* Staatsangehörigkeit
* Konfession, Religionsteilnahme, Religionsgrund
* Zugang zur Schule
* Herkunftsschule
* Sorgeberechtigte
* Fremdsprachenfolge
* Fächer mit Unterrichtsart und Kursnummer
* Bemerkung
* Laufbahn (wird in das Feld Bemerkung übernommen)

### Ansicht Klassen
* Kürzel

### Ansicht Sorgeberechtigte
* Anrede, Vorname, Name
* Straße, PLZ, Ort
* Telefon (privat)
* Beruf


### Ansicht Schulen
* Name




