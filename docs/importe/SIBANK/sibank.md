# SIBANK

Der Import der SIBANK-Daten nach MAGELLAN erfolgt über die 32-Bit-ODBC-Schnittstelle von Microsoft. Über den ODBC-Treiber greift der MAGELLAN-Administrator direkt auf Dateien im Datenverzeichnis von SIBANK zu.

Beim Import der Daten aus SIBANK werden alle zu importierenden Daten als neue Daten für MAGELLAN aufgefasst. 

Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm SIBANK nach MAGELLAN. 

## Schritt 1: Installation einer leeren Datenbank

Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:
1.	Rufen Sie den MAGELLAN-Administrator auf.
2.	Wählen Sie ```Ansicht``` und dann ```Datenbankpflege```. Wählen Sie die Option ```Datenbankinhalte löschen```.
3.	Klicken Sie auf ```OK```, um mit dem Erzeugen einer neuen Datenbank zu beginnen. 

>ACHTUNG<br/>
Ihre bisherige Datenbank wird dabei gelöscht! Über die Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.

## Schritt 2: Mandanten und Zeitraum in MAGELLAN anlegen
In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Zeitraum und ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus SIBANK werden in MAGELLAN zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Zeitraum  und zu welchem Mandanten die Daten zugeordnet werden. Sinnvollerweise sollten in MAGELLAN je ein Zeitraum für das 1. und das 2. Halbjahr des aktuellen Schuljahres eingetragen werden. Zum Eintragen eines Zeitraums und eines Mandanten in MAGELLAN gehen Sie wie folgt vor.

1.	Rufen Sie MAGELLAN auf.
2.	Rufen Sie das Menü ```Verzeichnisse``` und dann den Menüpunkt ```Zeiträume``` auf.
3.	Fügen Sie im Dialogfenster ```Verzeichnis der Zeiträume``` die gewünschten Zeiträume ein.
4.	Tragen Sie unter ```Ansicht``` und dann Mandanten einen Mandanten ein. Dies ist im Regelfall Ihre eigene Schule.
5.	Verlassen Sie MAGELLAN.

## Schritt 3: Statistikschlüssel und Postleitzahlen importieren

Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Statistikschlüssel und die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehalten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:

1.	Wählen Sie dazu ```Ansicht``` und dann ```Datenimporte```. 
2.	Wählen Sie die Option ```Schlüsselverzeichnisse importieren```.
3.	Wählen Sie anschließend die Option ```Postleitzahlverzeichnis importieren```.

## Schritt 4: SIBANK-Schlüssel und MAGELLAN-Schlüsselverzeichnisse anpassen
>Schlüssel<br/>
Die Schlüssel in SIBANK müssen dabei den Schlüsselverzeichnissen in MAGELLAN entsprechen! Nur bei einer Übereinstimmung der jeweiligen Schlüssel können die Daten aus SIBANK korrekt in MAGELLAN eingelesen werden.

## Schritt 5: SIBANK-Daten importieren

Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der SIBANK-Daten beginnen. Gehen Sie dazu wie folgt vor:
1.	Rufen Sie den MAGELLAN-Administrator auf.
2.	Wählen Sie ```Ansicht``` und dann ```Datenimporte```. Wählen Sie die Option ```Daten aus Verwaltungsprogrammen importieren```. Wählen Sie dabei im Auswahlfeld die Option ```SIBANK (Niedersachsen)``` und klicken Sie dann auf ```Start```.
3.	Geben Sie im Dialogfenster ```Importiere SIBANK``` den Ordner der SIBANK-Daten an, wählen Sie einen Zeitraum, denen die aktuellen SIBANK-Daten zugeordnet werden sollen (z.B. "1. Halbjahr 02/03" oder "2. Halbjahr 02/03"). Klicken Sie dann auf ```OK```.
4.	Der Import kann je nach Hardwarekonfiguration und Umfang Ihrer SIBANK-Daten mehrere Minuten dauern. Nach Abschluss des Imports können Sie den MAGELLAN-Administrator wieder verlassen.



