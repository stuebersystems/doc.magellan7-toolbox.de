# BBZ/SEKI

Der Import der BBZ/SEKI-Daten nach MAGELLAN erfolgt über die 32-Bit-ODBC-Schnittstelle von Microsoft. Über den ODBC-Treiber greift der MAGELLAN-Administrator direkt auf die Dateien im Verzeichnis BBZ/SEKI zu.

Beim Import der Daten aus BBZ/SEKI werden alle zu importierenden Daten als neue Daten für Magellan aufgefasst. 
Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm BBZ/SEKI nach MAGELLAN.


## Schritt 1: Daten aus BBZ/SEKI exportieren

Voraussetzung für einen Export der Daten aus BBZ/SEKI ist eine lokale Installation des Programms. Im Netz installierte Versionen haben scheinbar keine Exportfunktionalität.<br>
Es folgt eine Auflistung der Datendateien, die Sie für einen MAGELLAN-Import aus OpenAccess heraus exportieren können.

| Originaldatei | Exportierte dBase-Datei | BBZ	 | SEKI | Inhalt |
| -- | -- | -- | -- | -- |
| ABT.DB | ABT.DBF | ja |  | Abteilungen |
| SCHUL.DB | SCHUL.DBF | ja | ja | Schulen |
| FI.DB | FI.DB | ja | ja | Betriebe |
| KLAV.DB | KLAV.DB | ja | ja | Klassendaten/Vollzeit |
| KLAB.DB | KLAB.DB | ja |  | Klassendaten/Teilzeit |
| LDAT.DB | LDAT.DBF |ja | ja | Lehrerdaten |
| BFS.DB | BFS.DB | ja | ja | Schülerdaten/Vollzeit |
| BF.DB | BF.DBF | ja | | Schülerdaten/Teilzeit |
| NEU.DB | NEU.DBF | ja | ja| Bewerberdaten |
| KLAN.DB | KLAN.DBF | ja | ja | Bewerbungsziele |

Wie Sie sehen, lassen sich einige Daten nur aus dem Programm BBZ heraus exportieren.
Zum Exportieren der Daten müssen Sie wie folgt vorgehen:
1.	Starten Sie BBZ bzw. SEKI
2.	Drücken Sie ESC, um in das OpenAccess-CMP-Menü zu gelangen
3.	Drücken Sie F8 und wählen Sie den Menüpunkt Daten_konvertieren
4.	Geben Sie die Quelldatei (DF-Datei) und Zieldatei (DBF-Datei) an und drücken Sie auf F10. Die Daten werden konvertiert. Quelle und Zieldatei unterscheiden sich nur in der Dateiendung (z.B. Quelldatei = ABT.DF und Zieldatei = ABT.DBF). 
5.	Wiederholen Sie die Vorgehensweise solange, bis Sie alle gewünschten Quelldateien exportiert haben.
Kopieren Sie anschließend alle erzeugten DBF-Datei in ein Verzeichnis, auf welches Sie für den späteren Import im MAGELLAN-Administrator zurückgreifen können.

## Schritt 2:Installation einer leeren Datenbank

Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:
1.	Rufen Sie den MAGELLAN-Administrator auf.
2.	Wählen Sie ```Ansicht > Datenbankpflege> Datenbankinhalte löschen```.
3.	Klicken Sie auf OK, um mit dem Erzeugen einer neuen Datenbank zu beginnen. 

> #### danger::Achtung!
>
> Ihre bisherige Datenbank wird dabei gelöscht! Über die Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.


## Schritt 3: Mandanten und Zeitraum in Magellan anlegen

In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Zeitraum und ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus BBZ/SEKI werden in MAGELLAN zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Zeitraum  und zu welchem Mandanten die Daten zugeordnet werden. Sinnvollerweise sollten in MAGELLAN je ein Zeitraum für das 1. und das 2. Halbjahr des aktuellen Schuljahres eingetragen werden. Zum Eintragen eines Zeitraums und eines Mandanten in MAGELLAN gehen Sie wie folgt vor.

1.	Rufen Sie MAGELLAN auf.
2.	Rufen Sie das Menü Verzeichnisse und dann den Menüpunkt Zeiträume auf.
3.	Fügen Sie im Dialogfenster Verzeichnis der Zeiträume die gewünschten Zeiträume ein.
4.	Tragen Sie unter Ansicht und dann Mandanten einen Mandanten ein. Die ist im Regelfall Ihre eigene Schule.
5.	Verlassen Sie MAGELLAN.

## Schritt 4: Statistikschlüssel und Postleitzahlen importieren

Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Statistikschlüssel und die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehalten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:

1.	Wählen Sie dazu ```Ansicht> Datenimporte```. 
2.	Wählen Sie die Option Schlüsselverzeichnisse importieren.
3.	Wählen Sie anschließend die Option Postleitzahlverzeichnis importieren.

## Schritt 5: BBZ/SEKI-Schlüssel an MAGELLAN-Schlüsselverzeichnisse anpassen

Beim Import der Daten aus BBZ / SEKI werden einige Schlüsselverzeichnisse benötigt, die mit den passenden Daten gefüllt sein müssen.

  Folgende Schlüsselverzeichnisse sind wichtig:
  
1.	Konfessionen: Die Landesanpassung installiert keine Konfessionen. Sie müssen die in BBZ/SEKI genutzten Konfessionen also nachtragen. Bitte achten Sie darauf, dass Sie dabei die gleichen Kürzel wie in BBZ/SEKI verwenden.
2.	Beispiel: Die Konfession "evangelisch" ist in BBZ bzw. SEKI meist mit "ev" eingetragen. Sie müssen also im Schlüsselverzeichnis "Konfessionen" einen neuen Eintrag hinzufügen mit dem Kürzel = "ev" und der Bezeichnung = "evangelisch". 
3.	Staatsangehörigkeiten: Das Verzeichnis der Staatsangehörigkeiten wird zwar durch die Landesanpassung installiert, allerdings müssen die Kürzel angepasst werden.
4.	Beispiel: Die Staatsangehörigkeit "Deutsch" ist in BBZ bzw. SEKI meist mit "DEU" eingetragen. Sie müssen also im Schlüsselverzeichnis "Staatsangehörigkeiten" das Kürzel für "Deutschland" von "0" auf "DEU" umsetzen.
5.	Schulformen: Das Verzeichnis der Schulformen wird ebenfalls durch die Landesanpassung installiert. Überprüfen Sie bitte, ob die offiziellen Schlüs-sel mit denen in BBZ bzw. SEKI übereinstimmen. Gegebenenfalls müssen Sie auch hier Korrekturen durchführen.
So bearbeiten Sie ein Schlüsselverzeichnis:
6.	Starten Sie MAGELLAN.
7.	Klicken Sie auf ```Verzeichnisse > Weitere Schlüsselverzeichnisse```.
8.	Wählen Sie die gewünschte Schlüsseltabelle aus und klicken Sie auf Bearbeiten.


## Schritt 6: BBZ/SEKI-Daten importieren

Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der BBZ/SEKI-Daten beginnen. Gehen Sie dazu wie folgt vor:

1.	Rufen Sie den MAGELLAN-Administrator auf.
2.	Wählen Sie ```Ansicht> Datenimporte> Daten aus Verwaltungsprogrammen importieren```. Wählen Sie dabei im Auswahlfeld die Option BBZ/SEKI (Saarland) und klicken Sie dann auf Start.
3.	Geben Sie im Dialogfenster Importiere BBZ/SEKI den Ordner der BBZ/SEKI-Daten an, wählen Sie einen Zeitraum, denen die aktuellen BBZ/SEKI-Daten zugeordnet werden sollen (z.B. "1. Halbjahr 02/03" oder "2. Halbjahr 02/03"). Zusätzlich müssen Sie auch den Mandanten festlegen. Klicken Sie dann auf OK.
4.	Der Import kann je nach Hardwarekonfiguration und Umfang Ihrer BBZ/SEKI-Daten mehrere Minuten dauern. Nach Abschluss des Imports können Sie den MAGELLAN-Administrator wieder verlassen.
