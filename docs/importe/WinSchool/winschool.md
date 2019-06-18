# WinSchool {#WinSchool}

Der Import der WinSchool-Daten nach MAGELLAN ist möglich für die Versionen:

* WinSchool 1.7
* WinSchool 2000/2004 
* WinSchool SQL

Beim Import der Daten aus WinSchool werden alle zu importierenden Daten als neue Daten für MAGELLAN aufgefasst.   
Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm WinSchool nach MAGELLAN.

## Schritt 1: Installation einer leeren Datenbank {#Schritt1}

Bevor Sie eine leere Datenbank erzeugen, müssen Sie das Programm MAGELLAN installiert haben. Anschließend erzeugen Sie eine leere Datenbank inkl. Schlüsseltabellen wie folgt:

Rufen Sie den MAGELLAN-Administrator auf.  
Wählen Sie Ansicht und dann Datenbankpflege. Wählen Sie die Option Datenbankinhalte löschen.  
Klicken Sie auf OK, um mit dem Erzeugen einer neuen Datenbank zu beginnen.

> #### danger::Achtung!
>
> Ihre bisherige Datenbank wird dabei gelöscht! Überdie Optionen können Sie angeben, ob Sie die Schlüsselverzeichnisse bzw. Postleitzahlen beibehalten wollen.

## Schritt 2: Mandanten und Zeitraum in MAGELLAN anlegen {#Schritt2}

In der neu erzeugten MAGELLAN-Datenbank muss mindestens ein Zeitraum und ein Mandant eingetragen werden. Die aktuellen Schülerdaten aus WinSchool werden in MAGELLAN zeitraum- und mandantenbezogen abgelegt. Dementsprechend muss beim Import festgelegt werden, zu welchem Zeitraum  und zu welchem Mandanten die Daten zugeordnet werden. Sinnvollerweise sollten in MAGELLAN je ein Zeitraum für das 1. und das 2. Halbjahr des aktuellen Schuljahres eingetragen werden. Zum Eintragen eines Zeitraums und eines Mandanten in MAGELLAN gehen Sie wie folgt vor.

1. Rufen Sie MAGELLAN auf.
2. Rufen Sie das Menü `Verzeichnisse` und dann den Menüpunkt `Zeiträume` auf.
3. Fügen Sie im Dialogfenster `Verzeichnis der Zeiträume` die gewünschten Zeiträume ein.
4. Tragen Sie unter `Ansicht` und dann Mandanten einen Mandanten ein, dass ist im Regelfall Ihre eigene Schule.
5. Verlassen Sie MAGELLAN.

## Schritt 3: Postleitzahlen importieren {#Schritt3}

Nachdem eine neue leere Datenbank erzeugt worden ist, müssen Sie die Statistikschlüssel und die Postleitzahlen importieren, wenn Sie diese vor dem Löschen der Datenbank in Schritt 1 nicht beibehalten haben. Zum Import der Schlüssel und der Postleitzahlen gehen Sie wie folgt vor:  

1.    Wählen Sie dazu `Ansicht` und dann `Datenimporte`.   
2.    Wählen Sie die Option `Schlüsselverzeichnisse importieren`.  
3.    Wählen Sie anschließend die Option `Postleitzahlverzeichnis importieren`.

## Schritt 4: WinSchool-Daten importieren {#Schritt4}

Sie haben nun alle Voraussetzungen für den Import erfüllt und können mit dem eigentlichen Import der WinSchool-Daten beginnen. Gehen Sie dazu wie folgt vor:  

1. Rufen Sie den MAGELLAN-Administrator auf.  

2. Wählen Sie `Ansicht` und dann `Datenimporte`. Wählen Sie die Option `Daten aus Verwaltungsprogrammen importieren`. Wählen Sie dabei im Auswahlfeld die Option `WinSchool` und klicken Sie dann auf `Start`.  

3. Im folgenden Assistenten wählen Sie die verwendete WinSchool Version aus. Sie wählen zwischen WinSchool 1.7, WinSchool 2000/2004 oder WinSchool SQL. Geben Sie anschließend den Mandanten und den Zeitraum aus, in die die Daten übertragen werden sollen und bestätigen mit `OK`.  
  
   ![](/assets/images/importe/winschool-1.png)
  
4. Für WinSchool 1.7 oder WinSchool 2000/2004: Geben Sie im Dialogfenster Importiere WinSchool den Ordner der WinSchool-Daten an.   

5. Klicken Sie dann auf `OK`.  

6. Für WinSchool SQL: Geben Sie bitte den Namen ihres Hosts und den Namen Ihres SQL-Servers an. Es wird automatisch auf die wsdata.mdf zugegriffen. Klicken Sie anschließend auf `OK`.  
  
   ![](/assets/images/importe/winschool-2.png) 

Der Import kann je nach Hardwarekonfiguration und Umfang Ihrer WinSchool-Daten mehrere Minuten dauern. Nach Abschluss des Imports können Sie den Magellan-Administrator wieder verlassen.

## Importierte Felder {#ImportierteFelder}

Folgende Felder werden aus dem aus WinSchool 1.7/WinSchool 2000/2004 oder WinSchool SQL exportierten Format in die Schülerdatei des MAGELLAN-Importformates übernommen:

| Nr. | Feldname bei Win-SchoolExportdatei | Feldname im MAGELLAN-Importformat \(Schülerdaten\) |
| --- | --- | --- |
| - | **Lehrer**: | - |
| 1 | Kürzel | Kuerzel |
| 2 | Name | Nachname |
| 3 | Vorname | Vorname |
| 4 | Geschlecht | Geschlecht |
| 5 | Geburtsdatum | Geburtsdatum |
| 6 | Straße | Strasse |
| 7 | PLZ | PLZ |
| 8 | Ort | Ort |
| 9 | Telefon | Telefon |
| 10 | Telefax | Telefax |
| 11 | EMail | Email |
| 12 | Kfz1 | KFZ1 |
| 13 | Kfz2 | KFZ2 |
| 14 | Staatsangehörigkeit | Staatsangeh |
| 15 | Konfession | Konfession |
| 16 | PersonalNr | Personalnummer |
| - | **Betriebe**: | - |
| 17 | Kürzel | Kuerzel |
| 18 | Name1 | Name1 |
| 19 | Name2 | Name2 |
| 20 | Straße | Strasse |
| 21 | PLZ | PLZ |
| 22 | Ort | Ort |
| 23 | Telefon | Telefon |
| 24 | Telefax | Telefax |
| 25 | Bemerkungen | Bemerkung |
| - | **Klassen**: | - |
| 26 | Kurzform | Kuerzel |
| 27 | Bezeichnung | Langname1 |
| 28 | Bemerkungen | Bemerkung |
|  | 29 | Klassenzeiträume: |
| - | Klassenlehrer | Klassenleiter1 |
| 30 | Klassenlehrervertreter | Klassenleiter2 |
| - | **Sorgeberechtigte**: | - |
| 31 | Name | Nachname |
| 32 | Vorname | Vorname |
| 33 | Anrede | Anrede |
| 34 | Strasse | Strasse |
| 35 | PLZ | PLZ |
| 36 | Wohnort | Ort |
| 37 | Telefon | TelefonPrivat |
| 38 | EMail | Email |
| 39 | Beruf | Beruf |
|  | 40 | **Schüler**: |
| 41 | Name | Nachname |
|  | 42 | Vorname    Vorname |
| 43 | Geschlecht | Geschlecht |
| 44 | Geburtsdatum | Geburtsdatum |
| 45 | Geburtsort | Geburtsort |
| 46 | Strasse | Strasse |
| 47 | PLZ | PLZ |
| 48 | Wohnort | Ort |
| 49 | Telefon | Telefon |
| 50 | Telefax | Telefax |
| 51 | EMail | EMail |
| 52 | Tutor | Tutor |
| 53 | Staat | Staatsangeh1 |
| 54 | Kfz1 | KFZ |
| 55 | Aussiedler | Aussiedler |
| 56 | Bafög | Bafoeg |
| 57 | Gastschüler | Gastschueler |
| 58 | Aufnahmedatum | ZugangAm |
| 59 | Entlassungsdatum | AbgangAm |
| 60 | Bemerkung | Bemerkung |
| 64 | Klasse | Klasse |
| 66 | Ausbildungsbetrieb | Betrieb |



