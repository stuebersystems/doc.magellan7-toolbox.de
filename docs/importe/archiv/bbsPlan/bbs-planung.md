# BBS-Planung

Die Datenübernahme aus BBS-Planung ermöglicht den Import von Sorgeberechtigte-, Schüler- (inkl. Verbindung Schüler-Sorgeberechtige), Klassen- und Lehrerdaten nach MAGELLAN. Die BBS-Planung Access-Datenbank kann über den MAGELLAN-Importformat Konverter ausgelesen und die Daten in das MAGELLAN-Importformat konvertiert werden. 

Der Import erfolgt in drei Schritten:
1. Konvertieren in das MAGELLAN-Importformat
2. Vorbereiten der MAGELLAN-Datenbank
3. Import der Daten nach MAGELLAN

Die nachfolgenden Schritte beschreiben die Vorgehensweise für den Datenimport aus dem Schulverwaltungsprogramm BBS-Planung nach MAGELLAN.

## Übersicht der Importdateien die aus den BBS-Planung Daten erzeugt werden

|Importdatei | BBS-Planung - TABELLE | Beschreibung |
| -- | -- | -- |
| **lehrer.import.csv** | LVUEL | Enthält die Stammdaten der Lehrer |
| **sorgebe.import.csv** | SIL | Enthält die Stammdaten der Sorgeberechtigten |
| **klassen.import.csv**| KUL | Enthält die Stamm- und Zeitraumdaten der Klassen Bedingung: Vorhandensein der Zeiträume in Magellan |
| **schueler.import.csv**| SIL| Enthält die Stammdaten der Schüler und Bewerber |
|**schueler_laufbahn.import.csv** | Berechnet | Enthält die Laufbahndaten der Schüler. Wir berechnen anhand des Importdatums das aktuelle Schuljahr und legen zwei Schulhalbjahre an, in die die Schüler eingeschult werden. Weitere Bedingung: Import der klassen.import.csv|
|**schueler_sorgebe.import.csv**|SIL|Enthält die Zuordnung der Sorgeberechtigten zu den Schülern. Weitere Bedingung: Import der sorgebe.import.csv|

## Schritt 1: Konvertieren in das Magellan-Importformat

Navigieren Sie im Importformat Konverter über die Schalflächen „Zurück“ und „Weiter“, um zu den entsprechenden Seiten des Assistenten zu gelangen. Wenn Sie die Konvertierung starten, werden zuerst die Spaltennamen und die Pflichtfelder überprüft. Treten keine Probleme auf, werden die Quelldaten in die Zieldateien übernommen.

1. Starten Sie den MAGELLAN-Importformat Konverter über den Explorer. Rufen Sie dazu die Datei MAGELLANIFConv.exe im Programmordner von MAGELLAN (z.B. C:\Stueber Software\MAGELLAN 6\MAGELLANIFConv.exe).
2. Seite Anwendung – In der Auswahlbox für das Programm müssen Sie ```BBS-Planung``` auswählen.
3. Seite Quelle/Ziel – Geben Sie in das obere Feld den Pfad zur Datenbank ```s_daten.MDB``` an. Diese Datei enthält Ihre BBS-Planung Daten. 
4. Seite Quelle/Ziel – Geben Sie in das nächste Feld den Pfad zur Datei ```System.mdw``` an. Diese enthält die Zugriffsrechte, ohne die Sie sich nicht anmelden können.
5. Seite Quelle/Ziel – Im den nächsten beiden Feldern geben Sie bitte den Benutzernamen und das Passwort ein, um sich an der Datenbank anmelden zu können.
6. Seite Quelle/Ziel – Zuletzt geben Sie den Pfad an, in den die konvertierten MAGELLAN-Importformat Dateien gespeichert werden sollen.
7. Seite Der Assistent ist bereit – Klicken Sie auf ```Fertigstellen```, um die Konvertierung zu starten.
Nach der Konvertierung liegen die MAGELLAN-Importformatdateien im .CSV-Format in dem von Ihnen angegebenen Dateipfad.

## Schritt 2: Vorbereiten der MAGELLAN-Datenbank

Nach erfolgreicher Konvertierung sollte die MAGELLAN-Datenbank für den Import vorbereitet werden.

### MAGELLAN-Datenbank leeren

Üblicherweise liefert STÜBER SYSTEMS eine Datenbank mit Beispielinhalten. Diese Daten müssen vor dem Import gelöscht werden. Dazu gehen Sie bitte wie folgt vor.

1. Starten Sie den MAGELLAN-Administrator. 
2. Wählen Sie die Ansicht ```Datenbankpflege``` und führen Sie ```Datenbankinhalt löschen``` aus.
3. Markieren Sie den Haken bei ```Postleitzahlverzeichnis beibehalten```

### Zeiträume anlegen

Erstellen Sie alle in MAGELLAN notwendigen Zeiträume über ```Verzeichnisse > Zeiträume```. Die notwendigen Zeiträume erkennen Sie anhand des niedrigsten und höchsten Schuljahres in der schueler_laufbahn.import.csv bzw. anhand ihrer Schuljahre in BBS-Planung. Für Magellan wird pro Schuljahr ein Halbjahresdatensatz benötigt, Beispiel:

1. Halbjahr 2010/2011 – Von: 01.08.2010 Bis: 31.01.2011
2. Halbjahr 2011/2011 – Von: 01.02.2011 Bis: 31.07.2011

Diese genauen Datumsangaben sind für den Import vorgesehen und müssen eingetragen werden!

!!! info "Hinweis"

    Für den Import der BBS-Planung Daten ist lediglich das aktuelle Schuljahr in MAGELLAN einzutragen.

### Schlüsselverzeichnisse importieren

Importieren Sie die in MAGELLAN mitgelieferten Schlüsselverzeichnisse für Niedersachsen nach Magellan. Gehen Sie dabei wie folgt vor.

1. Starten Sie den MAGELLAN-Administrator. 
2. Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Schlüsselverzeichnisse importieren``` aus.
3. Geben Sie als Parameter ihr ```Bundesland```, Ihre ```Schulart```, den ```Mandanten``` und ```Alle Kataloge``` an.

### BBS-Planung-Schlüssel und Magellan-Schlüsselverzeichnisse anpassen

Die Schlüssel in BBS-Planung müssen dabei den Schlüsselverzeichnissen in Magellan entsprechen! Nur bei einer Übereinstimmung der jeweiligen Schlüssel können die Daten aus BBS-Planung korrekt in MAGELLAN eingelesen werden. Sie können die MAGELLAN Importformatdateien mit einem Texteditor oder in einer Tabellenkalkulation (z.B. LibreOffice Calc) bearbeiten und dort ggf. die zu importierenden Werte anpassen.


## Schritt 3: BBS-Planung-Daten importieren

Nach erfolgreicher Vorbereitung der Datenbank kann die Zieldatei über den MAGELLAN-Administrator importiert werden.
1. Starten Sie den MAGELLAN-Administrator.
2. Wählen Sie die Ansicht ```Datenimporte``` und führen Sie ```Daten über MAGELLAN-Importformat importieren``` aus.
Lesen Sie bitte im Kapitel [„MAGELLAN-Importformat“](/importe/MagImp/magellan-importformat.md), wie Sie die Daten korrekt nach Magellan importieren.

## Übersicht der unterstützten BBS-Planung Importfelder

In der nachfolgend aufgelisteten Tabelle erhalten Sie eine Übersicht der Daten, die für den Import von BBS-Planung nach MAGELLAN über das allgemeine Importformat und dem Importformat Konverter bereits unterstützt werden.

### lehrer.import.csv
| Feld in der Importdatei | Feld in BBS-Planung | Tabelle in BBS-Planung |
| -- | -- | -- |
| **Kuerzel** | NKURZ | LVUEL |
| **Vorname** | VNAME | LVUEL |
| **Nachname** | NNAME | LVUEL |
| **Geschlecht** | GESCHLECHT | LVUEL |
| **Geburtsdatum** | GEBDAT| LVUEL |
| **Strasse** | STR| LVUEL |
| **PLZ**| PLZ | LVUEL |
|**Ort**| ORT | LVUEL |
| **Telefon** | TEL | LVUEL |
| **Telefax** | FAX | LVUEL |
|**Mobil**| TEL2 | LVUEL |
| **Email** | ONLINE | LVUEL |
| **KFZ1** | KFZ | LVUEL |
| **Staatsangeh**| STAAT | LVUEL |
| **Konfession** | KONF | LVUEL |
| **Personalnr** | L_NR_STATI | LVUEL |
| **ZugangGrund** | ZUABGANG (je nach Schlüssel) | LVUEL |
| **AbgangGrund** | ZUABGANG (je nach Schlüssel) | LVUEL |
| **Dienstbez** | ADBEZ| LVUEL |
| **Bemerkung** | BEM | LVUEL |

### sorgebe.import.csv

|Feld in der Importdatei | Feld in BBS-Planung | Tabelle in BBS-Planung|
| -- | -- | -- |
| **Vorname** | E_VNAME, E_VNAME2 | SIL |
| **Nachname** | E_ANREDE, E_ANREDE2 | SIL |
| **Anrede** | E_ANREDE, E_ANREDE2 | SIL |
|  **Strasse** |E_STR, E_STR | SIL|
| **PLZ** | E_PLZ, E_PLZ2 | SIL |
| **Ort** | E_ORT, E_ORT2 |SIL |
|**TelefonPrivat** | E_TEL, E_TEL2 | SIL |
| **Email** | E_EMAIL, E_EMAIL2 | SIL |


### klassen.import.csv
|Feld in der Importdatei | Feld in BBS-Planung | Tabelle in BBS-Planung|
| -- | -- | -- |
| **Kuerzel** | KL_NAME | KUL |
| **ZeitraumVon** | Berechnet |  |
| **ZeitraumBis**|Berechnet |  |
| **Halbjahr** | Berechnet |  |
| **Klassenleiter1Kuerzel** | KL_LEHRER| KUL |
| **Klassenart** | S = Standardklasse |  |
| **Notenart** | N = Noten|  |
| **Bemerkung** | BEM | KUL |

### schueler.import.csv
| Feld in der Importdatei | Feld in BBS-Planung |Tabelle in BBS-Planung |
| -- | -- | -- |
|**Vorname** | VNAME | SIL |
|**Geburtsdatum** | GEBDAT | SIL |
| **Anrede **| GESCHLECHT (berechnet) | SIL |
| **Geburtsort** | GEBOR| SIL |
| **Strasse** | STR |SIL |
| **PLZ** |PLZ | SIL |
| **Ort** | ORT | SIL|
| **Telefon** | TEL | SIL |
| **Telefax** | FAX | SIL |
| **Staatsangeh1** | STAAT | SIL |
| **Konfession** |KONF | SIL |
| **Foerderung** | A_AMT | SIL |
| **Foerderbetrag** |BETRAG | SIL |
|**HoechsterAbschlussABS** | ABSCHLUSS | SIL |
| **Status**| S = Schüler |  |

### schueler_sorgebe.import.csv
| Feld in der Importdatei | Feld in BBS-Planung | Tabelle in BBS-Planung |
| -- | -- | -- |
|**SchuelerVorname** | VNAME | SIL |
|**SchuelerNachname** | NNAME| SIL |
| **SchuelerGeburtsdatum**| GEBDAT | SIL|
|**SorgebeVorname**|E_VNAME, E_VNAME2|SIL|
| **SorgebeNachname** | E_NNAME, E_NNAME2 |SIL|
| **SorgebeStrasse** | E_STR, E_STR| SIL|
| **SorgebeOrt** | E_ORT, E_ORT2 | SIL |
|**Verhaeltnis**|Berechnet|SIL |

### schueler_laufbahn.import.csv
| Feld in der Importdatei | Feld in Danis | Tabelle in Dani|
| -- | - | -- |
| **SchuelerVorname** | VNAME| SIL|
| **SchuelerNachname**| NNAME |SIL |
| **SchuelerGeburtsdatum** | GEBDAT | SIL |
| **KlasseKuerzel** | KL_NAME| SIL |
|**ZeitraumVon**| Berechnet | SIL |
|**ZeitraumBis** | Berechnet | SIL|
|**Halbjahr **| Berechnet | SIL |
|** Gewechselt** | Berechnet|SIL|
|**Wiederholer** | N = Kein Wiederholer |SIL |
| **Ueberspringer** | N = Kein Überspringer | SIL |








