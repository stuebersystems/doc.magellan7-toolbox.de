# SchoolExpert
Die Datenübernahme aus den Schulverwaltungsprogramm SchoolExpert erfolgt auf Basis der Export-schnittstelle in Schoolexpert, die den Export von Schüler-, Klassen- und Lehrerdaten ermöglicht. Der Import erfolgt in drei Schritten:

1.	Export der Daten aus SchoolExpert.
2.	Konvertieren der Textdateien in das MAGELLAN-Importformat über den MAGELLAN-Importformatkonverter. (z.B. C:\Stueber Software\Magellan 6\MagellanIFConv.exe).
3.	Import der Dateien im MAGELLAN-Importformat nach MAGELLAN.

## Schritt 1: Export der Daten aus SchoolExpert

Zum Export der Daten gehen Sie in SchoolExpert wie folgt vor:

1.	Rufen Sie in SchoolExpert ```Datei``` und ```Export von Dateien``` auf.
2.	Wählen Sie jetzt eine Tabelle z.B. Schueler.
3.	Geben Sie eine Exportdatei an z.B. Schueler.dbf.
4.	Wählen Sie das Exportformat Excel.
5.	Geben Sie bei Auswahl der Datensätze die Option ```Alle``` an.
6.	Klicken Sie auf ```Export ausführen```.
7.	Wiederholen Sie den Export gemäß 2.-6. für die Tabellen Personal und Klassen. 

## Schritt 2: Konvertieren der Exportdateien in das MAGELLAN-Importformat

Die aus Schoolexpert exportierten Dateien muss jetzt in das MAGELLAN-Importformat für Schüler-, Klassen- und Lehrerdaten gebracht werden. Dies erfolgt über den MAGELLAN-Importformatkonverter. Voraussetzung hierfür ist eine Installation von Excel auf dem Rechner.
1.	Starten Sie den MAGELLAN-Importformat Converter über den Explorer. Rufen Sie dazu die Datei MagellanIFConv.exe im Programmordner von MAGELLAN (z.B. C:\Stueber Software\Magellan 6\MagellanIFConv.exe).
2.	Wählen Sie in Abhängigkeit von Ihrer SchoolExpert Version unter Programm wählen die Option SchoolExpert (alte Version) oder SchoolExpert (Version 1.160) aus. Klicken Sie dann auf ```Weiter```.
3.	Wählen Sie für die Quelldatei den Konvertierungstyp Schüler und die zuvor aus SchoolExpert exportierte Datei für die Schülerdaten aus. Klicken Sie auf ```Weiter```.
4.	Geben Sie den gewünschten Namen der Zieldatei an und klicken Sie auf ```Weiter```.
5.	Klicken Sie auf ```Starten```, um die Konvertierung zu starten.
6.	Wiederholen Sie die Schritte 3-5 analog für die Klassen- und Lehrerdatei.

## Schritt 3: Daten nach MAGELLAN importieren

Die im 2. Schritt erzeugten Dateien entsprechen jetzt dem MAGELLAN-Importformat für Schüler-, Klassen- und Lehrerdaten. Diese Dateien müssen Sie jetzt über den MAGELLAN-Administrator nach MAGELLAN importieren. Wie Sie dazu vorgehen müssen, erfahren Sie im Kapitel MAGELLAN-Importformat.

## Importierte Felder

### SchoolExpert (alte Version)
Folgende Felder werden aus dem aus SchoolExpert (alteVersion) exportierten Format in die Schüler-, Klassen- bzw. Lehrerdatei des MAGELLAN-Importformates übernommen:

Nr.|	Feldname bei SchoolExpert-Exportdatei Schueler.xls	|Feldname im MAGELLAN-Importformat (Schülerdaten)
--|--|--
1	|Klasse|	Klasse
2	|Name	|Nachname
3	|Vorname|	Vorname
4	|Geschlecht	|Geschlecht
5	|Strasse|	Strasse
6	|PLZ|	PLZ
7	|Wohnort|	Ort
8	|Gemeindeschluessel	|Gemeinde
9	|Telefon|	Telefon
10|	Mobiltelefon	|Mobil
11	|E_Mail	|Email
12	|Geburtsort|	Geburtsort
13	|Geburtsdatum|	Geburtsdatum
14	|Einschulungsdatum|	Grundschuleintritt
15	|Eintrittsdatum	|ZugangAm
16	|Staatsangehoerigkeit	|Staatsangeh1
17	|Staatsangehoerigkeit2	|Staatsangeh2
18	|Religionszugehoerigkeit|	Konfession
19	|Funktion1	|Funktion1
20	|Funktion2|	Funktion2
21	|Erzieher1_Art|	Sorge1Verhaeltnis
22	|Erzieher1_Name	|Sorge1Nachname
23	|Erzieher1_Vorname	|Sorge1Vorname
24	|Erzieher1_Strasse	|Sorge1Strasse
25	|Erzieher1_PLZ	|Sorge1PLZ
26	|Erzieher1_Wohnort	|Sorge1Ort
27	|Erzieher1_Telefon_Privat	|Sorge1TelefonPrivat
28	|Erzieher1_Telefon_Firma|	Sorge1TelefonBeruf
29	|Erzieher1_Mobiltelefon|	Sorge1Mobil
30	|Erzieher1_E_Mail	|Sorge1Email
31	|Erzieher2_Art	|Sorge2Verhaeltnis
32	|Erzieher2_Name	|Sorge2Nachname
33	|Erzieher2_Vorname	|Sorge2Vorname
34	|Erzieher2_Strasse	|Sorge2Strasse
35	|Erzieher2_PLZ|	Sorge2PLZ
36	|Erzieher2_Wohnort|	Sorge2Ort
37	|Erzieher2_Telefon_Privat|	Sorge2TelefonPrivat
38|Erzieher2_Telefon_Firma	|Sorge2TelefonBeruf
39	|Erzieher2_Mobiltelefon	|Sorge2Mobil
40	|Erzieher2_E_Mail	|Sorge2Email
41	|Fremdsprache1	|Fremdsprache1
42|	Fremdsprache1_von|	Fremdsprache1Von
43	|Fremdsprache1_bis	|Fremdsprache1Bis
44	|Fremdsprache2	|Fremdsprache2
45|	Fremdsprache2_von	|Fremdsprache2Von
46	|Fremdsprache2_bis	|Fremdsprache2Bis
47	|Fremdsprache3	|Fremdsprache3
48	|Fremdsprache3_von|	Fremdsprache3Von
49	|Fremdsprache3_bis	|Fremdsprache3Bis
50	|Fremdsprache4|	Fremdsprache4
51	|Fremdsprache4_von	|Fremdsprache4Von
52	|Fremdsprache4_bis	|Fremdsprache4Bis
53|	Krankenkasse|	Krankenkasse

Nr.	|Feldname bei SchoolExpert-Exportdatei Lehrer.xls	|Feldname im Magellan-Importformat (Lehrerdaten)
--|--|--
1	|Kurzform	|Kuerzel
2	|Personalnummer	|PersonalNr
3	|Name	|Nachname
4	|Vorname	|Vorname
5	|Geburtsname|	Geburtsname
6	|Anrede	|Anrede
7	|Strasse	|Strasse
8	|PLZ	|PLZ
9	|Wohnort	|Ort
10	|Telefon_privat	|Telefon
11	|Telefax_privat	|Telefax
12	|Mobiltelefonnummer	|Mobil
13	|E_Mail	|Email
14	|Geschlecht	|Geschlecht
15	|Geburtdatum	|Geburtsdatum
16	|Familienstand	|Ehestand
17	|Staatsaneghörigkeit|	Staatsangeh
18	|Religionszugehörigkeit	|Konfession
19	|Amtsbezeichnung|	Amstbez
20	|Beschaeftigungsverh	|Beschaeftverh
21	|Zugang_am	|ZugangAm
22	|Zugnagsart	|ZugangGrund
23	|Abgangsart	|AbgangGrund

Nr.	|Feldname bei SchoolExpert-Exportdatei Klasse.xls|	Feldname im Magellan-Importformat (Klassendaten)
--|--|--
1	|Klasse	|Kuerzel
2	|Klassenleiter|	Klassenlehrer1
3	|Klassenleiter2	|Klassenlehrer2

### SchoolExpert (Version 1.160)
Folgende Felder werden aus dem aus SchoolExpert (Version 1.160) exportierten Format in die Schüler-, Klassen- bzw. Lehrerdatei des MAGELLAN-Importformates übernommen:

Nr.	|Feldname bei SchoolExpert-Exportdatei Schueler.xls|	Feldname im Magellan-Importformat (Schülerdaten)
--|--|--
1	|Klasse|	Klasse
2	|Name	|Nachname
3	|Vorname|	Vorname
4	|Geschlecht|	Geschlecht
5	|Strasse|	Strasse
6	|PLZ|	PLZ
7	|Wohnort	|Ort
8	|Geburtsname	|Geburtsname
9	|Telefon|Telefon
10	|Mobiltelefon|	Mobil
11	|E_Mail	|Email
12	|Geburtsort	|Geburtsort
13	|Geburtsdatum|	Geburtsdatum
14	|Einschulungsdatum	|Grundschuleintritt
15	|Eintrittsdatum	|ZugangAm
16	|Staatsangehoerigkeit|	Staatsangeh1
17	|Muttersprache	|Muttersprache
18	|Religionszugehoerigkeit	|Konfession
19	|Funktion1|	Funktion1
20	|Funktion2|	Funktion2
21	|Erzieher1_Art|	Sorge1Verhaeltnis
22	|Erzieher1_Name	|Sorge1Nachname
23	|Erzieher1_Vorname|	Sorge1Vorname
24	|Erzieher1_Strasse|	Sorge1Strasse
25	|Erzieher1_PLZ	|Sorge1PLZ
26	|Erzieher1_Wohnort|	Sorge1Ort
27	|Erzieher1_Telefon_Privat|	Sorge1TelefonPrivat
28	|Erzieher1_Telefon_Firma	|Sorge1TelefonBeruf
29	|Erzieher1_Mobiltelefon	|Sorge1Mobil
30	|Erzieher1_E_Mail	|Sorge1Email
31	|Erzieher2_Art	|Sorge2Verhaeltnis
32	|Erzieher2_Name	|Sorge2Nachname
33	|Erzieher2_Vorname	|Sorge2Vorname
34	|Erzieher2_Strasse	|Sorge2Strasse
35	|Erzieher2_PLZ	|Sorge2PLZ
36	|Erzieher2_Wohnort	|Sorge2Ort
37	|Erzieher2_Telefon_Privat	|Sorge2TelefonPrivat
38	|Erzieher2_Telefon_Firma	|Sorge2TelefonBeruf
39	|Erzieher2_Mobiltelefon	|Sorge2Mobil
40	|Erzieher2_E_Mail|	Sorge2Email
41	|Fremdsprache1	|Fremdsprache1
42	|Fremdsprache1_von|	Fremdsprache1Von
43	|Fremdsprache1_bis	|Fremdsprache1Bis
44	|Fremdsprache2	|Fremdsprache2
45	|Fremdsprache2_von|	Fremdsprache2Von
46	|Fremdsprache2_bis	|Fremdsprache2Bis
47	|Fremdsprache3	|Fremdsprache3
48	|Fremdsprache3_von	|Fremdsprache3Von
49	|Fremdsprache3_bis|	Fremdsprache3Bis
50	|Fremdsprache4|	Fremdsprache4
51	|Fremdsprache4_von	|Fremdsprache4Von
52	|Fremdsprache4_bis	|Fremdsprache4Bis
53	|Krankenkasse|	Krankenkasse

Nr.|	Feldname bei SchoolExpert-Exportdatei Lehrer.xls|	Feldname im Magellan-Importformat (Lehrerdaten)
--|--|--
1	|Kurzform	|Kuerzel
2	|Personalnummer|	PersonalNr
3	|Name	|Nachname
4	|Vorname|	Vorname
5	|Geburtsname|	Geburtsname
6	|Anrede	|Anrede
7	|Strasse|	Strasse
8	|PLZ|	PLZ
9	|Wohnort	|Ort
10	|Telefon_privat	|Telefon
11	|Telefax_privat	|Telefax
12	|Mobiltelefonnummer|	Mobil
13	|E_Mail	|Email
14	|Geschlecht|	Geschlecht
15	|Geburtdatum	|Geburtsdatum
16	|Familienstand|	Ehestand
17	|Staatsaneghörigkeit|	Staatsangeh
18	|Religionszugehörigkeit	|Konfession
19	|Amtsbezeichnung|	Amstbez
20	|Beschaeftigungsverh|	Beschaeftverh
21	|Zugang_am	|ZugangAm
22	|Zugnagsart	|ZugangGrund
23	|Abgangsart|	AbgangGrund

Nr.	|Feldname bei SchoolExpert-Exportdatei Klasse.xls|	Feldname im Magellan-Importformat (Klassendaten)
--|--|--
1	|Klasse|	Kuerzel
2	|Klassenleiter	|Klassenlehrer1
3	|Klassenleiter2	|Klassenlehrer2

