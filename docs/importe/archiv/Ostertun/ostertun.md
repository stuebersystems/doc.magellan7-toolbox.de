# Ostertun

Für den Import der Daten aus dem Schulverwaltungsprogramm von Herrn Ostertun müssen Sie zunächst die Daten aus dem Ostertun-Programm exportieren.

## Schritt 1: Daten aus Ostertun-Programm exportieren

Erzeugen Sie zunächst im Ostertun-Programm eine selbst definierte Liste mit folgenden Feldern:

Nr.	|Feld	|Exportname
--|--|
1.	|	Aussiedler	|Aussiedler
2.		|email	|EMail
3.		|Gast	|Gastschüler
4.		|GebDat|	Geburtsdatum
5.		|GebOrt	|Geburtsort
6.		|Geschlecht|	Geschlecht
7.	|	ID-Nummer|	ID
8.		|Konfession	|Konfession
9.		|MutErzBerechtigt|	MutErzBerechtigt
10.		|MutNachname|	MutNachname
11.		|MutVorname	|MutVorname
12.		|MutWohnort	|MutWohnort
13.		|Nachname	|Nachname
14.		|Nation	|Staatsangehörigkeit
15.		|Postleitzahl	|PLZ
16.		|Strasse	|Strasse
17.		|Telefon|	Telefon
18.		|VatErzberechtigt	|VatErzberechtigt
19.		|VatNachname	|VatNachname
20.		|VatStrasse|	VatStrasse
21.		|VatTelefon	|VatTelefon
22.		|VatVorname	|VatVorname
23.		|VatWohnort	|VatWohnort
24.		|Vorname	|Vorname
25.		|WohnortOhnePLZ	|Ort


Exportieren Sie diese Liste als dBase-Datenbank mit dem Namen OSTERTUN.DBF.

## Schritt 2: Installation einer leeren Datenbank

Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:
1.	Rufen Sie den ```MAGELLAN-Administrator``` auf.
2.	Wählen Sie Ansicht und dann ```Datenbankpflege```. Wählen Sie die Option ```Datenbankinhalte löschen```.
3.	Klicken Sie auf q, um mit dem Erzeugen einer neuen Datenbank zu beginnen. 

>ACHTUNG<br/>
Ihre bisherige Datenbank wird dabei gelöscht! Über die Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.

## Schritt 3: Mandanten in MAGELLAN anlegen

In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus Ostertun werden in MAGELLAN zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Mandanten die Daten zugeordnet werden. Zum Eintragen des Mandanten in MAGELLAN gehen Sie wie folgt vor.
1.	Rufen Sie ```MAGELLAN``` auf.
2.	Tragen Sie unter Ansicht und dann Mandanten einen Mandanten ein. Die ist im Regelfall Ihre eigene Schule.
3.	Verlassen Sie MAGELLAN.

## Schritt 4: Statistikschlüssel und Postleitzahlen importieren

Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Statistikschlüssel und die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehalten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:
1.	Wählen Sie dazu ```Ansicht``` und dann ```Datenimporte```. 
2.	Wählen Sie die Option ```Schlüsselverzeichnisse importieren```.
3.	Wählen Sie anschließend die Option ```Postleitzahlverzeichnis importieren```.

## Schritt 5: Ostertun-Daten importieren

Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der Ostertun-Daten beginnen. Gehen Sie dazu wie folgt vor:
1.	Rufen Sie den ```MAGELLAN-Administrator``` auf.
2.	Wählen Sie ```Ansicht``` und dann ```Datenimporte```. Wählen Sie die Option ```Daten aus Verwaltungsprogrammen importieren```. Wählen Sie dabei im Auswahlfeld die Option ```Ostertun (Schleswig-Holstein) ```und klicken Sie dann auf ```Weiter```.
3.	Geben Sie im Dialogfenster ```Importiere Ostertun``` den Ordner der in Schritt 1 exportieren Datei OSTERTUN.DBF an, wählen Sie einen Zeitraum, denen die aktuellen Ostertun-Daten zugeordnet werden sollen (z.B. "1. Halbjahr 02/03" oder "2. Halbjahr 02/03"). Zusätzlich müssen Sie auch den Mandanten festlegen. Klicken Sie dann auf ```OK```.
