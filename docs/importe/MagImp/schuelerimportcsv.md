# schueler.import.csv

Die Datei schueler.import.csv dient dem Import der Schüler-Stammdaten. Grundsätzlich wird, wie in allen anderen Importdateien jeder Schüler einmalig in MAGELLAN hinzugefügt, übereinstimmende Schüler (Vorname, Nachname, Geburtsdatum) werden übersprungen.

Eine Ausnahme stellt der Import der Schüler-Stammdaten dar, bei dem eine Aktualisierung unter vorgegebenen Bedingungen möglich ist.

Durch eine Übereinstimmung des Wertes im Feld **GUIDExtern**, wird der entsprechende Datensatz nicht eingefügt, sondern ein bestehender Datensatz in der MAGELLAN Datenbank aktualisiert.

Somit erhalten Sie die Möglichkeit zwischen einem Fremdprogramm und MAGELLAN unter Verwendung einer 36-stelligen GUID (Bsp.: 0D27F45C-E53D-4E81-AC0A-19D0B1BFA798) bestehende Schüler-Stammdaten wiederholt zu aktualisieren.

Einschränkung: Der Status des Schülers kann nicht verändert werden.

## Bewerber oder Schüler

Der Unterschied zwischen Schüler Bewerber und Abgänger wird anhand des Feldes „Status“ hergestellt.
Wenn das Feld „Status“ den Wert SB enthält, dann wird geprüft, ob der Schüler (mit Vornamen, Nachnamen, Geburtsdatum) bereits an der Schule aktiv war. In diesem Fall wird der Schüler als Bewerber importiert und Magellan merkt sich die ID des gefundenen Schülerdatensatzes im Feld „IDIntern“ in Magellan. Dies dient dem Zweck, die beiden getrennten Datensätze zu einem späteren Zeitpunkt in Magellan wieder vereinen zu können, um die Laufbahn zu komplettieren.
Es kann maximal nur ein Schüler/Bewerber die IDIntern eines anderen innehaben. Wenn bereits ein Bewerber oder Schüler mit einer IDIntern besteht, wird der Import des Datensatzes übersprungen.

## Felder

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feld         | Anmerkung
------------ | ---------
**Feldname** | GUIDExtern
Typ          | A
Größe        | 36
Bemerkung    | Zum Speichern einer 36-stelligen GUID (Ermöglicht durch Abgleich das Update des entsprechenden Datensatzes)
**Feldname** | Vorname
Typ          | A P
Größe        | 100
Bemerkung    | -
**Feldname** | Nachname
Typ          | A P
Größe        | 100
Bemerkung    | -
**Feldname** | Status
Typ          | A P
Größe        | 1
Bemerkung    | Mögliche Werte: <br/>B = Bewerber<br/>S = Schüler<br/>SB = Schueler/Bewerber*<br/>(siehe Erläuterungen oben)<br/>A = Abgänger
**Feldname** | Geburtsdatum
Typ          | D P
Größe        | -
Bemerkung    | -
**Feldname** | Anrede
Typ          | A
Größe        | 3
Bemerkung    | Mögliche Werte: <br/>F = Frau<br/>H = Herr<br/>FD= Frau Dr.<br/>HD = Herr Dr.<br/>FP = Frau Prof.<br/>HP = Herr Prof.<br/>FPD = Frau Prof. Dr.<br/>HPD = Herr Prof. Dr.<br/><br/>MS = Ms.<br/><br/>MRS = Mrs.<br/>MR = Mr.
**Feldname** | Geschlecht
Typ          | A
Größe        | 1
Bemerkung    | Mögliche Werte: <br/>W = weiblich<br/>M = männlich<br/>D = divers
**Feldname** | Geburtsort
Typ          | A
Größe        | 100
Bemerkung    | -
**Feldname** | Geburtsland
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“ (Kuerzel)
**Feldname** | Geburtsname
Typ          | A
Größe        | 30
Bemerkung    |-
**Feldname** | Strasse
Typ          | A
Größe        | 100
Bemerkung    | -
**Feldname** | Land
Typ          | A
Größe        | 3
Bemerkung    | Landeskennzeichen z.B. „D“
**Feldname** | PLZ
Typ          | A
Größe        | 10
Bemerkung    | Postleitzahl
**Feldname** | Ort
Typ          | A
Größe        | 100
Bemerkung    | Ort
**Feldname** | Ortsteil
Typ          | A
Größe        | 100
Bemerkung    | -
**Feldname** | Gemeinde
Typ          | A V
Größe        | 8
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Gemeinden“ (Postleitzahlen)
**Feldname** | Telefon
Typ          | A
Größe        | 30
Bemerkung    | -
**Feldname** | Telefax
Typ          | A
Größe        | 30
Bemerkung    | -
**Feldname** | Mobil
Typ          | A
Größe        | 30
Bemerkung    |-
**Feldname** | EMail
Typ          | A
Größe        | 100
Bemerkung    | -
**Feldname** | Wohnform
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Wohnformen“ (Kuerzel)
**Feldname** | NichtDeutscheHerkunft
Typ          | L
Größe        | 1
Bemerkung    | -
**Feldname** | Staatsangeh1 / Staatsangeh2
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Staatsangehoerigkeiten“ (Kuerzel)
**Feldname** | Muttersprache / Verkehrssprache
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Muttersprachen“ (Kuerzel)
**Feldname** | Sprachgruppe
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Sprachgruppen“ (Kuerzel)
**Feldname** | Konfession
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Konfessionen“ (Kuerzel)
**Feldname** | RelWunsch
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „RelWuensche“ (Kuerzel)
**Feldname** | RelTeilnahme
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „RelTeilnahmen“ (Kuerzel)
**Feldname** | RelGrund
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „RelGruende“ (Kuerzel)
**Feldname** | RelAbmeldungVon
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | RelAbmeldungBis
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | Umschulung
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Umschulungsmerkmale“ (Kuerzel)
**Feldname** | Personalnr
Typ          | A
Größe        | 15
Bemerkung    | Personalnummer
**Feldname** | Krankenkasse
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Krankenkassen“ (Kuerzel)
**Feldname** | Versicherungsart
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Versicherungsarten“ (Kuerzel)
**Feldname** | Fahrschueler
Typ          | L
Größe        | -
Bemerkung    | -
**Feldname** | Fahrstrecke
Typ          | A
Größe        | 50
Bemerkung    |
**Feldname** | FahrstreckeKM
Typ          | N
Größe        | -
Bemerkung    | -
**Feldname** | Einstiegsstelle
Typ          | A
Größe        | 50
Bemerkung    |
**Feldname** | Verkehrsmittel
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Verkehrsmittel“ (Kuerzel)
**Feldname** | Fahrgeld
Typ          | A
Größe        | 18
Bemerkung    | -
**Feldname** | FahrgeldbewVon
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | FahrgeldbewBis
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | Fahrkarte
Typ          | A V
Größe        | 20
Bemerkung    | Verweis auf das Schlüsselverzeichnis „Fahrkarten“ (Kuerzel)
**Feldname** | FahrkarteGueltigVon
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | FahrkarteGueltigBis
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | KFZ
Typ          | A
Größe        | 15
Bemerkung    | KFZ-Kennzeichen des Schülers
**Feldname** | Aussiedler
Typ          | L
Größe        | -
Bemerkung    | -
**Feldname** | AussiedlerSeit
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | Auslaender
Typ          | L
Größe        | -
Bemerkung    | -
**Feldname** | AuslaenderSeit
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | InDeutschlandSeit
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | AufenthaltserlaubnisBis
Typ          | D
Größe        | 10
Bemerkung    | In der Form TT.MM.JJJJ
**Feldname** | SchulpflichtErfuellt
Typ          | L
Größe| -
Bemerkung| -
**Feldname**| Bafoeg
Typ| L
Größe|-
Bemerkung|-
**Feldname**| BafoegBis
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| Integrationsschueler
Typ| L
Größe|-
Bemerkung|-
**Feldname**| Gastschueler
Typ| L
Größe|-
Bemerkung|-
**Feldname**| GastschulgeldUeberwiesen
Typ| L
Größe|-
Bemerkung|-
**Feldname**| Bildungskarte
Typ| A
Größe| 2
Bemerkung| Mögliche Werte: <br/>HE = Heim<br/>HO = Hort<br/>I = Internat
**Feldname**| BildungskarteBis
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| Foerderung
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Foerderungen“ (Kuerzel)
**Feldname**| Foerdernr
Typ| A
Größe| 8
Bemerkung| Fördernummer
**Feldname**| Foerderbetrag
Typ| N
Größe| -
Bemerkung|-
**Feldname**| Unterstuetzung
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Unterstuetzungen“ (Kuerzel)
**Feldname**| BewerbungAm
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| Bewerbungsziel1<br/>Bewerbungsziel2<br/>Bewerbungsziel3<br/>Bewerbungsziel4
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Bewerbungsziele“ (Kuerzel)
**Feldname**| BewerberStatus
Typ| A
Größe| 2
Bemerkung| Mögliche Werte: <br/>WA = Auf Warteliste<br/>B1 = Angenommen für Bewerbungsziel 1<br/>B2 = Angenommen für Bewerbungsziel 2<br/>B3 = Angenommen für Bewerbungsziel 3<br/>B4 = Angenommen für Bewerbungsziel 4<br/>NA = nicht angenommen<br/>BT = Beratungstest<br/>BG = Beratungsgespräch<br/>NE = Nicht zum Gespräch/Test erschienen<br/>AB = Aufnahmebescheid<br/>ZN = Zusage nicht zurück<br/>AG = Abgemeldet
**Feldname**| BewerberNote
Typ| N
Größe| -
Bemerkung| -
**Feldname**| BewerberPunkte
Typ| N
Größe| -
Bemerkung| -
**Feldname**| Fremdsprache1 / Fremdsprache2 / Fremdsprache3 / Fremdsprache4
Typ| A
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Faecher“ (Kuerzel)
**Feldname**| Fremdsprache1Von<br/>Fremdsprache2Von<br/>Fremdsprache3Von<br/>Fremdsprache4Von
Typ| S
Größe|-
Bemerkung| Von-Wert der Klassenstufe
**Feldname**| Fremdsprache1Bis<br/>Fremdsprache2Bis<br/>Fremdsprache3Bis<br/>Fremdsprache4Bis
Typ| S
Größe| -
Bemerkung| Bis-Wert der Klassenstufe
**Feldname**| Fremdsprache1Status<br/>Fremdsprache2Status<br/>Fremdsprache3Status<br/>Fremdsprache4Status
Typ| A
Größe| 2
Bemerkung| Mögliche Werte: <br/>BS = Unterricht an berichtender Schule<br/>AS = Unterricht an anderer Schule<br/>AN = Unterricht anerkannt<br/>AB = Unterricht abgewählt<br/>WU = Wahlunterricht<br/>FA = Fach<br/>HF = Hauptfach<br/>ER = Ergänzendes Fach
**Feldname**| Grundschuleintritt
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| Einschulung
Typ| A
Größe| 1
Bemerkung| Mögliche Werte: <br/>V = Vorzeitige Einschulung<br/>F = Fristgerechte Einschulung<br/>S = Verspätete Einschulung
**Feldname**| HoechsterBildungsgangABS
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
**Feldname**| HoechsterAbschlussABS
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „AbschluesseExtern“ (Kuerzel)
**Feldname**| HoechsterAbschlussABSAm
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| HoechsterBildungsgangBBS
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Bildungsgaenge“ (Kuerzel)
**Feldname**| HoechsterAbschlussBBS
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „AbschluesseExtern“ (Kuerzel)
**Feldname**| HoechsterAbschlussBBSAm
Typ| D
Größe| 10
Bemerkung| In der Form TT.MM.JJJJ
**Feldname**| HoechsterAbschlussBBSBeruf
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Berufe“ (Kuerzel)
**Feldname**| ZugangAm
Typ| D
Größe| -
Bemerkung| Zugangsdatum zur Schule in der Form TT.MM.JJJJ
**Feldname**| Abgang
Typ| A
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „Abgangsarten“ (Kuerzel)
**Feldname**| AbgangAm
Typ| D
Größe| -
Bemerkung| Abgangsdatum in der Form TT.MM.JJJJ
**Feldname**| Bemerkung
Typ| M
Größe| 255
Bemerkung| -
**Feldname**| MerkmalA1 / MerkmalA2 / MerkmalA3 / MerkmalA4 / MerkmalA5 / MerkmalA6
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „KlassenMerkmale“ (Kuerzel) <br/>Freies Merkmal
**Feldname**| MerkmalB1 / MerkmalB2 / MerkmalB3 / MerkmalB4
Typ| A
Größe| 15
Bemerkung| Freies Textmerkmal
**Feldname**| MerkmalD1 / MerkmalD2 / MerkmalD3 / MerkmalD4
Typ| D
Größe| 10
Bemerkung| Freies Datumsmerkmal in der Form TT.MM.JJJJ
**Feldname**| MerkmalS1<br/>MerkmalS2<br/>MerkmalS3<br/>MerkmalS4<br/>MerkmalS5<br/>MerkmalS6<br/>MerkmalS7<br/>MerkmalS8<br/>MerkmalS9<br/>MerkmalS10
Typ| A V
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis „SchuelerMerkmale“ (Kuerzel) <br/>Statistikmerkmal
**Feldname**| MerkmalT1<br/>MerkmalT2<br/>MerkmalT3<br/>MerkmalT4
Typ| A
Größe| 15
Bemerkung| eventuell reserveriert als Statistikmerkmal (Text): bitte schauen Sie in der Dokumentation Landesstatistiken nach, ob das Feld für statistische Eingaben reserviert ist
**Feldname**| MerkmalU1<br/>MerkmalU2
Typ| D
Größe| 10
Bemerkung| Statistikmerkmal (Datum) in der Form TT.MM.JJJJ
**Feldname**| Wahlfach1<br/>Wahlfach2<br/>Wahlfach3<br/>Wahlfach4
Typ| A
Größe| 20
Bemerkung| Verweis auf das Schlüsselverzeichnis "Faecher" (Kuerzel)

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schueler.import.csv, Stand: 30.06.2017

GUIDExtern
Vorname
Nachname
Status
Geburtsdatum
Anrede
Geschlecht
Geburtsort
Geburtsland
Geburtsname
Strasse
Land
PLZ
Ort
Ortsteil
Gemeinde
Telefon
Telefax
Mobil
EMail
Wohnform
Staatsangeh1
Staatsangeh2
NichtDeutscheHerkunft
Muttersprache
Verkehrssprache
Sprachgruppe
Konfession
RelWunsch
RelTeilnahme
RelGrund
RelAbmeldungVon
RelAbmeldungBis
Umschulung
Personalnr
Krankenkasse
Versicherungsart
Fahrschueler
Fahrstrecke
FahrstreckeKM
Einstiegsstelle
Verkehrsmittel
Fahrgeld
FahrgeldbewVon
FahrgeldbewBis
Fahrkarte
FahrkarteGueltigVon
FahrkarteGueltigBis
KFZ
Aussiedler
SchulpflichtErfuellt
Bafoeg
BafoegBis
Integrationsschueler
Gastschueler
GastschulgeldUeberwiesen
Bildungskarte
BildungskarteBis
Foerderung
Foerdernr
Foerderbetrag
Unterstuetzung
BewerbungAm
Bewerbungsziel1
Bewerbungsziel2
Bewerbungsziel3
Bewerbungsziel4
BewerberStatus
Bewerbernote
Bewerberpunkte
Fremdsprache1
Fremdsprache2
Fremdsprache3
Fremdsprache4
Fremdsprache1Von
Fremdsprache2Von
Fremdsprache3Von
Fremdsprache4Von
Fremdsprache1Bis
Fremdsprache2Bis
Fremdsprache3Bis
Fremdsprache4Bis
Fremdsprache1Status
Fremdsprache2Status
Fremdsprache3Status
Fremdsprache4Status
Grundschuleintritt
Einschulung
HoechsterBildungsgangABS
HoechsterAbschlussABS
HoechsterAbschlussABSAm
HoechsterBildungsgangBBS
HoechsterAbschlussBBS
HoechsterAbschlussBBSAm
HoechsterAbschlussBBSBeruf
ZugangAm
Abgang
AbgangAm
Bemerkung
MerkmalA1
MerkmalA2
MerkmalA3
MerkmalA4
MerkmalA5
MerkmalA6
MerkmalB1
MerkmalB2
MerkmalB3
MerkmalB4
MerkmalD1
MerkmalD2
MerkmalD3
MerkmalD4
MerkmalS1
MerkmalS2
MerkmalS3
MerkmalS4
MerkmalS5
MerkmalS6
MerkmalS7
MerkmalS8
MerkmalS9
MerkmalS10
MerkmalT1
MerkmalT2
MerkmalT3
MerkmalT4
MerkmalU1
MerkmalU2

!!! info "Hinweis"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
