# ISL-Schule

Für den Import der Daten aus dem Schulverwaltungsprogramm ISL-Schule greift der MAGELLAN-Administrator auf die Datei DATEN.MDB von ISL-Schule zu. Die Datei muss im ACCESS97-Format vorliegen. Sollte Sie eine ältere Version von ISL-Schule besitzen, so müssen Sie die Datenbank DA-TEN.MDB aus dem ACCESS 2.0-Format zunächst in der Version ACCESS97 konvertieren. Mit Hilfe von Microsoft-Access 97 können Sie die ISL-Datei DATEN.MDB aus dem ACCESS 2.0-Format in das AC-CESS97-Format konvertieren.

Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm ISL-Schule nach MAGELLAN.

## Schritt 1: Installation einer leeren Datenbank


Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:
1. Rufen Sie den MAGELLAN-Administrator auf.
1. Wählen Sie Ansicht und dann Datenbankpflege. Wählen Sie die Option Datenbankinhalte löschen.
2. Klicken Sie auf OK, um mit dem Erzeugen einer neuen Datenbank zu beginnen.


> #### danger::Achtung!
>
>  Ihre bisherige Datenbank wird dabei gelöscht! Über die Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.

## Schritt 2: Mandanten in MAGELLAN anlegen
In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus ISL-Schule werden in Magellan zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Mandanten die Daten zugeordnet werden. Zum Eintragen des Mandanten in MAGELLAN gehen Sie wie folgt vor.
1. Rufen Sie MAGELLAN auf.
2. Tragen Sie unter Ansicht und dann Mandanten einen Mandanten ein. Die ist im Regelfall Ihre eigene Schule.
3. Verlassen Sie MAGELLAN.

## Schritt 3: Postleitzahlen importieren


Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehalten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:
1. Wählen Sie dazu Ansicht und dann ```Datenimporte```.
2. Wählen Sie die Option ```Postleitzahlverzeichnis importieren```.

## Schritt 4: ISL-Daten importieren


Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der ISL-Daten beginnen. Gehen Sie dazu wie folgt vor:
1. Rufen Sie den MAGELLAN-Administrator auf.
2. Wählen Sie Ansicht und dann ```Datenimporte```. Wählen Sie die Option ```Daten aus Verwaltungsprogrammen importieren```. Wählen Sie dabei im Auswahlfeld die Option ISL-Schule und klicken Sie dann auf Weiter.
3. Wählen Sie zwei Halbjahre aus ISL-Schule aus und klicken Sie dann auf ```Start```.
4. Geben Sie im Dialogfenster Importiere ISL-Schule den Ordner der ISL-Datei DATEN.MDB an, wählen Sie einen Zeitraum, denen die aktuellen ISL-Schule-Daten zugeordnet werden sollen (z.B. "1. Halbjahr 02/03" oder "2. Halbjahr 02/03"). Zusätzlich müssen Sie auch den Mandanten festlegen. Klicken Sie dann auf OK.


