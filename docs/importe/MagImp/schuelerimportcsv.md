# Schnittstellenformat schueler.import.csv

Die Datei schueler.import.csv dient dem Import der Schüler-Stammdaten.

## Bestehende Schüler aktualisieren

Durch eine Übereinstimmung des Wertes im Feld **GUIDExtern**, wird der entsprechende Datensatz nicht eingefügt, sondern ein bestehender Datensatz in der MAGELLAN Datenbank aktualisiert.

Somit erhalten Sie die Möglichkeit zwischen einem Fremdprogramm und MAGELLAN unter Verwendung einer 36-stelligen GUID (Bsp.: 0D27F45C-E53D-4E81-AC0A-19D0B1BFA798) bestehende Schüler-Stammdaten wiederholt zu aktualisieren.

Einschränkung: Der Status des Schülers kann nicht verändert werden.

## Bewerber oder Schüler

Der Unterschied zwischen Schüler Bewerber und Abgänger wird anhand des Feldes „Status“ hergestellt.
Wenn das Feld „Status“ den Wert `SB` enthält, dann wird geprüft, ob der Schüler (mit `Vornamen`, `Nachnamen`, `Geburtsdatum`) bereits an der Schule aktiv war. In diesem Fall wird der Schüler als Bewerber importiert und Magellan merkt sich die ID des gefundenen Schülerdatensatzes im Feld „IDIntern“ in Magellan. Dies dient dem Zweck, die beiden getrennten Datensätze zu einem späteren Zeitpunkt in Magellan wieder vereinen zu können, um die Laufbahn zu komplettieren.
Die Daten des Stammschülers (Beispielsweise Adressdaten auf `Daten1` oder Herkunftsabschlüsse auf `Daten2`) werden mit den Daten des Nebenschülers aktualisiert.
Dieses Vorgehen ist nur beim ersten Import und Erkennen des Stammschülers gegeben, eine weitere Nebenlaufbahn kann auf diesem Weg nicht erzeugt werden.

!!! warning "Wichtig!"

    Es kann maximal nur ein Schüler/Bewerber die IDIntern eines anderen innehaben. Wenn bereits ein Bewerber oder Schüler mit einer IDIntern besteht, wird der Import des Datensatzes übersprungen.

## Felder

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Beschriftung  | Name                           | Typ | Größe
------------- | ------------------------------ | --- | -----
Feldname      | **GUIDExtern**                 | A   | 36
Bemerkung     | Zum Speichern einer 36-stelligen GUID (Ermöglicht durch Abgleich das Update des entsprechenden Datensatzes)
Feldname      | **Vorname**                    | A P | 100
Feldname      | **Nachname**                   | A P | 100
Feldname      | **Status**                     | A P | 1
Bemerkung     | Mögliche Werte: <br/>B = Bewerber<br/>S = Schüler<br/>SB = Schueler/Bewerber*<br/>(siehe Erläuterungen oben)<br/>A = Abgänger
Feldname      | **Geburtsdatum**               | D P | -
Feldname      | **Anrede**                     | A   | 3
Bemerkung     | Mögliche Werte: <br/>F = Frau<br/>H = Herr<br/>FD= Frau Dr.<br/>HD = Herr Dr.<br/>FP = Frau Prof.<br/>HP = Herr Prof.<br/>FPD = Frau Prof. Dr.<br/>HPD = Herr Prof. Dr.<br/><br/>MS = Ms.<br/><br/>MRS = Mrs.<br/>MR = Mr.
Feldname      | **Geschlecht**                 | A   | 1
Bemerkung     | Mögliche Werte: <br/>W = weiblich<br/>M = männlich<br/>D = divers
Feldname      | **Geburtsort**                 | A   | 100
Feldname      | **Geburtsland**                | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“ (Kuerzel)
Feldname      | **Geburtsname**                | A   | 30
Feldname      | **Strasse**                    | A   | 100
Feldname      | **Land**                       | A   | 3
Bemerkung     | Landeskennzeichen z.B. „D“
Feldname      | **PLZ**                        | A   | 10
Bemerkung     | Postleitzahl
Feldname      | **Ort**                        | A   | 100
Feldname      | **Ortsteil**                   | A   | 100
Feldname      | **Gemeinde**                   | A V | 8
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Gemeinden“ (Postleitzahlen)
Feldname      | **Telefon**                    | A   | 30
Feldname      | **Telefax**                    | A   | 30
Feldname      | **Mobil**                      | A   | 30
Feldname      | **EMail**                      | A   | 100
Feldname      | **Wohnform**                   | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Wohnformen“ (Kuerzel)
Feldname      | **NichtDeutscheHerkunft**           | L   | 1
Feldname      | **Staatsangeh1 / Staatsangeh2**     | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“ (Kuerzel)
Feldname      | **Muttersprache / Verkehrssprache** | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Muttersprachen“ (Kuerzel)
Feldname      | **Sprachgruppe**               | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Sprachgruppen“ (Kuerzel)
Feldname      | **Konfession**                 | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Konfessionen“ (Kuerzel)
Feldname      | **RelWunsch**                  | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „RelWuensche“ (Kuerzel)
Feldname      | **RelTeilnahme**               | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „RelTeilnahmen“ (Kuerzel)
Feldname      | **RelGrund**                   | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „RelGruende“ (Kuerzel)
Feldname      | **RelAbmeldungVon**            | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **RelAbmeldungBis**            | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Umschulung**                 | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Umschulungsmerkmale“ (Kuerzel)
Feldname      | **Personalnr**                 | A   | 15
Bemerkung     | Personalnummer
Feldname      | **Krankenkasse**               | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Krankenkassen“ (Kuerzel)
Feldname      | **Versicherungsart**           | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Versicherungsarten“ (Kuerzel)
Feldname      | **Fahrschueler**               | L   | 1
Feldname      | **Fahrstrecke**                | A   | 50
Feldname      | **FahrstreckeKM**              | N   | -
Feldname      | **Einstiegsstelle**            | A   | 50
Feldname      | **Verkehrsmittel**             | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Verkehrsmittel“ (Kuerzel)
Feldname      | **Fahrgeld**                   | A   | 18
Feldname      | **FahrgeldbewVon**             | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **FahrgeldbewBis**             | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Fahrkarte**                  | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Fahrkarten“ (Kuerzel)
Feldname      | **FahrkarteGueltigVon**        | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **FahrkarteGueltigBis**        | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **KFZ**                        | A   | 15
Bemerkung     | KFZ-Kennzeichen des Schülers
Feldname      | **Aussiedler**                 | L   | 1
Feldname      | **AussiedlerSeit**             | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Auslaender**                 | L   | 1
Feldname      | **AuslaenderSeit**             | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **InDeutschlandSeit**          | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **AufenthaltserlaubnisBis**    | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **SchulpflichtErfuellt**       | L   | 1
Feldname      | **Bafoeg**                     | L   | 1
Feldname      | **BafoegBis**                  | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Integrationsschueler**       | L   | 1
Feldname      | **Gastschueler**               | L   | 1
Feldname      | **GastschulgeldUeberwiesen**   | L   | 1
Feldname      | **Bildungskarte**              | A   | 2
Bemerkung     | Mögliche Werte: <br/>HE = Heim<br/>HO = Hort<br/>I = Internat
Feldname      | **BildungskarteBis**           | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Foerderung**                 | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Foerderungen“ (Kuerzel)
Feldname      | **Foerdernr**                  | A   | 8
Bemerkung     | Fördernummer
Feldname      | **Foerderbetrag**              | N   | -
Feldname      | **Unterstuetzung**             | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Unterstuetzungen“ (Kuerzel)
Feldname      | **BewerbungAm**                | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Bewerbungsziel1 / Bewerbungsziel2 / Bewerbungsziel3 / Bewerbungsziel4** | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Bewerbungsziele“ (Kuerzel)
Feldname      | **BewerberStatus**             | A   | 2
Bemerkung     | Mögliche Werte: <br/>WA = Auf Warteliste<br/>B1 = Angenommen für Bewerbungsziel 1<br/>B2 = Angenommen für Bewerbungsziel 2<br/>B3 = Angenommen für Bewerbungsziel 3<br/>B4 = Angenommen für Bewerbungsziel 4<br/>NA = nicht angenommen<br/>BT = Beratungstest<br/>BG = Beratungsgespräch<br/>NE = Nicht zum Gespräch/Test erschienen<br/>AB = Aufnahmebescheid<br/>ZN = Zusage nicht zurück<br/>AG = Abgemeldet
Feldname      | **BewerberNote**               | N   | -
Feldname      | **BewerberPunkte**             | N   | -
Feldname      | **Fremdsprache1 / Fremdsprache2 / Fremdsprache3 / Fremdsprache4** | A   | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Faecher“ (Kuerzel)
Feldname      | **Fremdsprache1Von / Fremdsprache2Von / Fremdsprache3Von / Fremdsprache4Von** | S   | -
Bemerkung     | Von-Wert der Klassenstufe
Feldname      | **Fremdsprache1Bis / Fremdsprache2Bis / Fremdsprache3Bis / Fremdsprache4Bis** | S   | -
Bemerkung     | Bis-Wert der Klassenstufe
Feldname      | **Fremdsprache1Status / Fremdsprache2Status / Fremdsprache3Status / Fremdsprache4Status** | A   | 2
Bemerkung     | Mögliche Werte: <br/>BS = Unterricht an berichtender Schule<br/>AS = Unterricht an anderer Schule<br/>AN = Unterricht anerkannt<br/>AB = Unterricht abgewählt<br/>WU = Wahlunterricht<br/>FA = Fach<br/>HF = Hauptfach<br/>ER = Ergänzendes Fach
Feldname      | **Grundschuleintritt**         | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **Einschulung**                | A   | 1
Bemerkung     | Mögliche Werte: <br/>V = Vorzeitige Einschulung<br/>F = Fristgerechte Einschulung<br/>S = Verspätete Einschulung
Feldname      | **HoechsterBildungsgangABS**   | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
Feldname      | **HoechsterAbschlussABS**      | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „AbschluesseExtern“ (Kuerzel)
Feldname      | **HoechsterAbschlussABSAm**    | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **HoechsterBildungsgangBBS**   | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
Feldname      | **HoechsterAbschlussBBS**      | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „AbschluesseExtern“ (Kuerzel)
Feldname      | **HoechsterAbschlussBBSAm**    | D   | 10
Bemerkung     | In der Form TT.MM.JJJJ
Feldname      | **HoechsterAbschlussBBSBeruf** | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Berufe“ (Kuerzel)
Feldname      | **ZugangAm**                   | D   | 10
Bemerkung     | Zugangsdatum zur Schule in der Form TT.MM.JJJJ
Feldname      | **Abgang**                     | A   | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „Abgangsarten“ (Kuerzel)
Feldname      | **AbgangAm**                   | D   | 10
Bemerkung     | Abgangsdatum in der Form TT.MM.JJJJ
Feldname      | **Bemerkung**                  | M   | 255
Feldname      | **MerkmalA1 / MerkmalA2 / MerkmalA3 / MerkmalA4 / MerkmalA5 / MerkmalA6** | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „SchuelerMerkmale“ (Kuerzel) <br/>Freies Merkmal
Feldname      | **MerkmalB1 / MerkmalB2 / MerkmalB3 / MerkmalB4** | A   | 100
Bemerkung     | Freies Textmerkmal
Feldname      | **MerkmalD1 / MerkmalD2 / MerkmalD3 / MerkmalD4** | D   | 10
Bemerkung     | Freies Datumsmerkmal in der Form TT.MM.JJJJ
Feldname      | **MerkmalS1 / MerkmalS2 / MerkmalS3 / MerkmalS4 / MerkmalS5 / MerkmalS6 / MerkmalS7 / MerkmalS8 / MerkmalS9 / MerkmalS10** | A V | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis „SchuelerMerkmale“ (Kuerzel) <br/>Statistikmerkmal
Feldname      | **MerkmalT1 / MerkmalT2 / MerkmalT3 / MerkmalT4** | A   | 15
Bemerkung     | eventuell reserveriert als Statistikmerkmal (Text): bitte schauen Sie in der Dokumentation Landesstatistiken nach, ob das Feld für statistische Eingaben reserviert ist
Feldname      | **MerkmalU1<br/>MerkmalU2**    | D   | 10
Bemerkung     | Statistikmerkmal (Datum) in der Form TT.MM.JJJJ
Feldname      | **Wahlfach1 / Wahlfach2 / Wahlfach3 / Wahlfach4** | A   | 20
Bemerkung     | Verweis auf das Schlüsselverzeichnis "Faecher" (Kuerzel)

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schueler.import.csv, Stand: 23.02.2021

```csv
"Vorname";"Nachname";"Status";"Geburtsdatum";"Anrede";"Geschlecht";"Geburtsort";"Geburtsland";"Geburtsname";"Strasse";"Land";"PLZ";"Ort";"Ortsteil";"Gemeinde";"Telefon";"Telefax";"Mobil";"EMail";"Wohnform";"Staatsangeh1";"Staatsangeh2";"NichtDeutscheHerkunft";"Muttersprache";"Verkehrssprache";"Sprachgruppe";"Konfession";"RelWunsch";"RelTeilnahme";"RelGrund";"RelAbmeldungVon";"RelAbmeldungBis";"Umschulung";"Personalnr";"Krankenkasse";"Versicherungsart";"Fahrschueler";"Fahrstrecke";"FahrstreckeKM";"Einstiegsstelle";"Verkehrsmittel";"Fahrgeld";"FahrgeldbewVon";"FahrgeldbewBis";"Fahrkarte";"FahrkarteGueltigVon";"FahrkarteGueltigBis";"KFZ";"Aussiedler";"SchulpflichtErfuellt";"Bafoeg";"BafoegBis";"Integrationsschueler";"Gastschueler";"GastschulgeldUeberwiesen";"Bildungskarte";"BildungskarteBis";"Foerderung";"Foerdernr";"Foerderbetrag";"Unterstuetzung";"BewerbungAm";"Bewerbungsziel1";"Bewerbungsziel2";"Bewerbungsziel3";"Bewerbungsziel4";"BewerberStatus";"Bewerbernote";"Bewerberpunkte";"Fremdsprache1";"Fremdsprache2";"Fremdsprache3";"Fremdsprache4";"Fremdsprache1Von";"Fremdsprache2Von";"Fremdsprache3Von";"Fremdsprache4Von";"Fremdsprache1Bis";"Fremdsprache2Bis";"Fremdsprache3Bis";"Fremdsprache4Bis";"Fremdsprache1Status";"Fremdsprache2Status";"Fremdsprache3Status";"Fremdsprache4Status";"Grundschuleintritt";"Einschulung";"HoechsterBildungsgangABS";"HoechsterAbschlussABS";"HoechsterAbschlussABSAm";"HoechsterBildungsgangBBS";"HoechsterAbschlussBBS";"HoechsterAbschlussBBSAm";"HoechsterAbschlussBBSBeruf";"ZugangAm";"Abgang";"AbgangAm";"Bemerkung";"MerkmalA1";"MerkmalA2";"MerkmalA3";"MerkmalA4";"MerkmalA5";"MerkmalA6";"MerkmalB1";"MerkmalB2";"MerkmalB3";"MerkmalB4";"MerkmalD1";"MerkmalD2";"MerkmalD3";"MerkmalD4";"MerkmalS1";"MerkmalS2";"MerkmalS3";"MerkmalS4";"MerkmalS5";"MerkmalS6";"MerkmalS7";"MerkmalS8";"MerkmalS9";"MerkmalS10";"MerkmalT1";"MerkmalT2";"MerkmalT3";"MerkmalT4";"MerkmalU1";"MerkmalU2"
```

!!! info "Hinweis"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
