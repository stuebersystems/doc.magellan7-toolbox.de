# View SchuelerAnsicht

Grundlage sind die Tabellen:

* [Schueler](https://doc.magellan7-toolbox.stueber.de/datenstruktur/tabellen/Schueler/)
* [SchuelerZeitraeume](https://doc.magellan7-toolbox.stueber.de/datenstruktur/tabellen/SchuelerZeitraeume/)
* [KlassenZeitraeume](https://doc.magellan7-toolbox.stueber.de/datenstruktur/tabellen/KlassenZeitraeume/)

| Feldname                      | Typ | Größe | Funktion | Bemerkung |
|-------------------------------|-----|-------|----------|-----------|
| Mandant                       | I   | -     | -        | -         |
| ID                            | I   | -     | -        | -         |
| GUID                          | A   | 32    | -        | -         |
| IDIntern                      | I   | -     | -        | -         |
| IDExtern                      | I   | -     | -        | -         |
| GUIDExtern                    | A   | 36    | -        | -         |
| KlassenZeitraumID             | I   | -     | -        | -         |
| SchuelerZeitraumID            | I   | -     | -        | -         |
| Klasse                        | I   | -     | -        | -         |
| Zeitraum                      | I   | -     | -        | -         |
| Gewechselt                    | L   | 1     | -        | -         |
| Barcode                       | A   | 20    | -        | -         |
| BarcodePrint                  | A   | 20    | -        | -         |
| Nachname                      | A   | 100   | -        | -         |
| NachnameNative                | A   | 100   | -        | -         |
| Namenszusatz                  | A   | 100   | -        | -         |
| NamenszusatzNative            | A   | 100   | -        | -         |
| Vorname                       | A   | 100   | -        | -         |
| VornameNative                 | A   | 100   | -        | -         |
| Vorname2                      | A   | 100   | -        | -         |
| Vorname2Native                | A   | 100   | -        | -         |
| Anrede                        | A   | 1     | -        | -         |
| Geschlecht                    | A   | 1     | -        | -         |
| Geburtsdatum                  | D   | -     | -        | -         |
| Geburtsort                    | A   | 100   | -        | -         |
| Geburtskreis                  | A   | 100   | -        | -         |
| Geburtsland                   | A   | 10    | -        | -         |
| Geburtsname                   | A   | 50    | -        | -         |
| Strasse                       | A   | 100   | -        | -         |
| Adresszusatz                  | A   | 200   | -        | -         |
| Land                          | A   | 3     | -        | -         |
| PLZ                           | A   | 10    | -        | -         |
| Ort                           | A   | 100   | -        | -         |
| Ortsteil                      | A   | 100   | -        | -         |
| Adressgebiet                  | A   | 300   | -        | -         |
| Gemeinde                      | A   | 8     | -        | -         |
| Stadtbezirk                   | A   | 10    | -        | -         |
| Telefon                       | A   | 30    | -        | -         |
| Telefax                       | A   | 30    | -        | -         |
| Mobil                         | A   | 30    | -        | -         |
| EMail                         | A   | 100   | -        | -         |
| Tutor                         | I   | -     | -        | -         |
| Wohnform                      | A   | 10    | -        | -         |
| Staatsangeh1                  | A   | 10    | -        | -         |
| Staatsangeh2                  | A   | 10    | -        | -         |
| Muttersprache                 | A   | 10    | -        | -         |
| Verkehrssprache               | A   | 10    | -        | -         |
| SopaedFoerderung              | A   | 10    | -        | -         |
| FoerderSchwerpunkt1           | A   | 10    | -        | -         |
| FoerderSchwerpunkt2           | A   | 10    | -        | -         |
| Sprachgruppe                  | A   | 10    | -        | -         |
| Konfession                    | A   | 10    | -        | -         |
| RelWunsch                     | A   | 10    | -        | -         |
| RelTeilnahme                  | A   | 10    | -        | -         |
| RelGrund                      | A   | 10    | -        | -         |
| RelAbmeldungVon               | D   | -     | -        | -         |
| RelAbmeldungBis               | D   | -     | -        | -         |
| Umschulung                    | A   | 10    | -        | -         |
| Funktion1                     | A   | 10    | -        | -         |
| Funktion2                     | A   | 10    | -        | -         |
| Funktion3                     | A   | 10    | -        | -         |
| Funktion4                     | A   | 10    | -        | -         |
| Funktion5                     | A   | 10    | -        | -         |
| Funktion6                     | A   | 10    | -        | -         |
| Funktion7                     | A   | 10    | -        | -         |
| Funktion8                     | A   | 10    | -        | -         |
| Personalnr                    | A   | 15    | -        | -         |
| Beeintraechtigung             | A   | 200   | -        | -         |
| Behinderung                   | A   | 10    | -        | -         |
| Krankenkasse                  | A   | 10    | -        | -         |
| Versicherungsart              | A   | 10    | -        | -         |
| NotfallPerson                 | A   | 50    | -        | -         |
| NotfallTelefon                | A   | 30    | -        | -         |
| Fahrschueler                  | L   | -     | -        | -         |
| Fahrstrecke                   | A   | 50    | -        | -         |
| FahrstreckeKM                 | N   | -     | -        | -         |
| Einstiegsstelle               | A   | 50    | -        | -         |
| Verkehrsmittel                | A   | 10    | -        | -         |
| Fahrgeld                      | N   | -     | -        | -         |
| FahrgeldbewVon                | D   | -     | -        | -         |
| FahrgeldbewBis                | D   | -     | -        | -         |
| Fahrkarte                     | A   | 10    | -        | -         |
| FahrkarteGueltigVon           | D   | -     | -        | -         |
| FahrkarteGueltigBis           | D   | -     | -        | -         |
| KFZ                           | A   | 15    | -        | -         |
| Status                        | S   | -     | -        | -         |
| Profil                        | A   | 10    | -        | -         |
| Aussiedler                    | L   | -     | -        | -         |
| AussiedlerSeit                | D   | -     | -        | -         |
| Auslaender                    | L   | -     | -        | -         |
| AuslaenderSeit                | D   | -     | -        | -         |
| InDeutschlandSeit             | D   | -     | -        | -         |
| AufenthaltserlaubnisBis       | D   | -     | -        | -         |
| SchulpflichtErfuellt          | L   | -     | -        | -         |
| Bafoeg                        | L   | -     | -        | -         |
| BafoegBis                     | D   | -     | -        | -         |
| Integrationsschueler          | L   | -     | -        | -         |
| Gastschueler                  | L   | -     | -        | -         |
| GastschulgeldUeberwiesen      | L   | -     | -        | -         |
| Foerderung                    | A   | 10    | -        | -         |
| Foerdernr                     | A   | 20    | -        | -         |
| Foerderbetrag                 | N   | -     | -        | -         |
| Unterstuetzung                | A   | 10    | -        | -         |
| Betreuung                     | S   | -     | -        | -         |
| BetreuungAdresse              | I   | -     | -        | -         |
| MittagessenTeilnahme          | L   | -     | -        | -         |
| GanztagbetriebGebunden        | S   | -     | -        | -         |
| GanztagbetriebOffen           | S   | -     | -        | -         |
| BewerbungAm                   | D   | -     | -        | -         |
| Bewerbungsziel1               | A   | 10    | -        | -         |
| Bewerbungsziel2               | A   | 10    | -        | -         |
| Bewerbungsziel3               | A   | 10    | -        | -         |
| Bewerbungsziel4               | A   | 10    | -        | -         |
| BewerberStatus                | S   | -     | -        | -         |
| BewerberStatusAm              | D   | -     | -        | -         |
| BewerberHFNote                | N   | -     | -        | -         |
| BewerberNote                  | N   | -     | -        | -         |
| BewerberPunkte                | N   | -     | -        | -         |
| BewerberRangzahl              | S   | -     | -        | -         |
| BewerberRangzahlZiel1         | N   | -     | -        | -         |
| BewerberRangzahlZiel2         | N   | -     | -        | -         |
| BewerberRangzahlZiel3         | N   | -     | -        | -         |
| BewerberRangzahlZiel4         | N   | -     | -        | -         |
| Fremdsprache1                 | A   | 10    | -        | -         |
| Fremdsprache1Von              | S   | -     | -        | -         |
| Fremdsprache1Bis              | S   | -     | -        | -         |
| Fremdsprache1Status           | S   | -     | -        | -         |
| Fremdsprache1Status2          | S   | -     | -        | -         |
| Fremdsprache1Note             | N   | -     | -        | -         |
| Fremdsprache1Referenz         | A   | 10    | -        | -         |
| Fremdsprache2                 | A   | -     | -        | -         |
| Fremdsprache2Von              | S   | -     | -        | -         |
| Fremdsprache2Bis              | S   | -     | -        | -         |
| Fremdsprache2Status           | S   | -     | -        | -         |
| Fremdsprache2Status2          | S   | -     | -        | -         |
| Fremdsprache2Note             | N   | -     | -        | -         |
| Fremdsprache2Referenz         | A   | 10    | -        | -         |
| Fremdsprache3                 | A   | -     | -        | -         |
| Fremdsprache3Von              | S   | -     | -        | -         |
| Fremdsprache3Bis              | S   | -     | -        | -         |
| Fremdsprache3Status           | S   | -     | -        | -         |
| Fremdsprache3Status2          | S   | -     | -        | -         |
| Fremdsprache3Note             | N   | -     | -        | -         |
| Fremdsprache3Referenz         | A   | 10    | -        | -         |
| Fremdsprache4                 | A   | -     | -        | -         |
| Fremdsprache4Von              | S   | -     | -        | -         |
| Fremdsprache4Bis              | S   | -     | -        | -         |
| Fremdsprache4Status           | S   | -     | -        | -         |
| Fremdsprache4Status2          | S   | -     | -        | -         |
| Fremdsprache4Note             | N   | -     | -        | -         |
| Fremdsprache4Referenz         | A   | 10    | -        | -         |
| Wahlfach1                     | I   | -     | -        | -         |
| Wahlfach2                     | I   | -     | -        | -         |
| Wahlfach3                     | I   | -     | -        | -         |
| Wahlfach4                     | I   | -     | -        | -         |
| Wahlfach5                     | I   | -     | -        | -         |
| Wahlfach6                     | I   | -     | -        | -         |
| Ausbildung                    | I   | -     | -        | -         |
| Grundschuleintritt            | D   | -     | -        | -         |
| Einschulung                   | S   | -     | -        | -         |
| HoechsterBildungsgangABS      | A   | 10    | -        | -         |
| HoechsterAbschlussABS         | A   | 10    | -        | -         |
| HoechsterAbschlussABSSchule   | I   | -     | -        | -         |
| HoechsterAbschlussABSAm       | D   | -     | -        | -         |
| HoechsterAbschlussABSNote     | N   | -     | -        | -         |
| HoechsterBildungsgangBBS      | A   | 10    | -        | -         |
| HoechsterAbschlussBBS         | A   | 10    | -        | -         |
| HoechsterAbschlussBBSSchule   | I   | -     | -        | -         |
| HoechsterAbschlussBBSAm       | D   | -     | -        | -         |
| HoechsterAbschlussBBSNote     | N   | -     | -        | -         |
| HoechsterAbschlussBBSAustritt | D   | -     | -        | -         |
| HoechsterAbschlussBBSBeruf    | A   | 10    | -        | -         |
| HoechsterAbschlussBBSBerufAm  | D   | -     | -        | -         |
| Berufsjahre                   | N   | -     | -        | -         |
| Anmeldestatus                 | S   | -     | -        | -         |
| ZugangAm                      | D   | -     | -        | -         |
| Zugang2Am                     | D   | -     | -        | -         |
| HerkunftSchule                | I   | -     | -        | -         |
| Einschulmerkmal               | A   | 10    | -        | -         |
| Einschulmerkmal2              | A   | 10    | -        | -         |
| Einschulmerkmal3              | A   | 10    | -        | -         |
| EinschulungAntrag             | L   | -     | -        | -         |
| EinschulungAbgebendeSchule    | I   | -     | -        | -         |
| EinschulungBemerkung          | M   | -     | -        | -         |
| VoraussichtlichesEnde         | D   | -     | -        | -         |
| Ueberweisung                  | L   | -     | -        | -         |
| UeberweisungAm                | D   | -     | -        | -         |
| Abgang                        | A   | 10    | -        | -         |
| AbgangAm                      | D   | -     | -        | -         |
| Abgang2Am                     | D   | -     | -        | -         |
| Uebergang                     | A   | 10    | -        | -         |
| UebergangAnSchule             | I   | -     | -        | -         |
| UebergangAnSchulform          | A   | 10    | -        | -         |
| UebergangAm                   | D   | -     | -        | -         |
| UebergangKlassenstufe         | A   | 10    | -        | -         |
| UebergangUnterlagen           | L   | -     | -        | -         |
| UebergangFoerderUnterlagen    | L   | -     | -        | -         |
| UebergangZeugnis              | L   | -     | -        | -         |
| UebergangGeaendertAm          | D   | -     | -        | -         |
| UebergangGeaendertVon         | D   | -     | -        | -         |
| MerkmalA1                     | A   | 10    | -        | -         |
| MerkmalA2                     | A   | 10    | -        | -         |
| MerkmalA3                     | A   | 10    | -        | -         |
| MerkmalA4                     | A   | 10    | -        | -         |
| MerkmalA5                     | A   | 10    | -        | -         |
| MerkmalA6                     | A   | 10    | -        | -         |
| MerkmalS1                     | A   | 10    | -        | -         |
| MerkmalS2                     | A   | 10    | -        | -         |
| MerkmalS3                     | A   | 10    | -        | -         |
| MerkmalS4                     | A   | 10    | -        | -         |
| MerkmalS5                     | A   | 10    | -        | -         |
| MerkmalS6                     | A   | 10    | -        | -         |
| MerkmalS7                     | A   | 10    | -        | -         |
| MerkmalS8                     | A   | 10    | -        | -         |
| MerkmalS9                     | A   | 10    | -        | -         |
| MerkmalS10                    | A   | 10    | -        | -         |
| MerkmalB1                     | A   | 100   | -        | -         |
| MerkmalB2                     | A   | 100   | -        | -         |
| MerkmalB3                     | A   | 100   | -        | -         |
| MerkmalB4                     | A   | 100   | -        | -         |
| MerkmalT1                     | A   | 100   | -        | -         |
| MerkmalT2                     | A   | 100   | -        | -         |
| MerkmalT3                     | A   | 100   | -        | -         |
| MerkmalT4                     | A   | 100   | -        | -         |
| MerkmalD1                     | A   | 100   | -        | -         |
| MerkmalD2                     | A   | 100   | -        | -         |
| MerkmalD3                     | A   | 100   | -        | -         |
| MerkmalD4                     | A   | 100   | -        | -         |
| MerkmalU1                     | A   | 100   | -        | -         |
| MerkmalU2                     | A   | 100   | -        | -         |
| Auskunft                      | S   | -     | -        | -         |
| AuswaertigerSchueler          | A   | 10    | -        | -         |
| AusstellungBehoerde           | A   | 100   | -        | -         |
| AusstellungBehoerdeDatum      | D   | -     | -        | -         |
| BetreuungInnerschulisch1      | A   | 10    | -        | -         |
| BetreuungInnerschulisch2      | A   | 10    | -        | -         |
| BetreuungInnerschulisch3      | A   | 10    | -        | -         |
| BetreuungAusserschulisch1     | A   | 10    | -        | -         |
| BetreuungAusserschulisch2     | A   | 10    | -        | -         |
| BetreuungAusserschulisch3     | A   | 10    | -        | -         |
| Schulbesuchsjahr              | S   | -     | -        | -         |
| Ausbildungsjahr               | S   | -     | -        | -         |
| Fachkombination               | A   | 4     | -        | -         |
| TeilnahmeZusatzangebot        | L   | -     | -        | -         |
| SportBefreit                  | L   | -     | -        | -         |
| Unterrichtstage               | S   | -     | -        | -         |
| Fehltage                      | S   | -     | -        | -         |
| FehltageU                     | S   | -     | -        | -         |
| Fehlstunden                   | S   | -     | -        | -         |
| FehlstundenU                  | S   | -     | -        | -         |
| Versaeumnisse                 | S   | -     | -        | -         |
| Verhalten                     | I   | -     | -        | -         |
| Mitarbeit                     | I   | -     | -        | -         |
| ZeugniskonferenzAm            | D   | -     | -        | -         |
| ZeugnisausgabeAm              | D   | -     | -        | -         |
| Anrechnungsdatum              | D   | -     | -        | -         |
| Durchschnitt1                 | N   | -     | -        | -         |
| Durchschnitt2                 | N   | -     | -        | -         |
| Durchschnitt3                 | N   | -     | -        | -         |
| Pruefungsvorsitz              | I   | -     | -        | -         |
| Jahrgang                      | S   | -     | -        | -         |
| AkteAngefordert               | L   | -     | -        | -         |
| LMAnteil                      | S   | -     | -        | -         |
| LMZahlungsstand               | S   | -     | -        | -         |
| LMZahlungsstandDatum          | D   | -     | -        | -         |
| LMZusatzbeitrag               | N   | -     | -        | -         |
| LMBefreit                     | L   | -     | -        | -         |
| LMBefreitBis                  | D   | -     | -        | -         |
| AusweisAusgestelltAm          | D   | -     | -        | -         |
| AusweisBemerkung              | A   | 150   | -        | -         |
| Bildungskarte                 | S   | -     | -        | -         |
| BildungskarteBis              | D   | -     | -        | -         |
| NichtDeutscheHerkunft         | L   | -     | -        | -         |
| SchuelerausweisBis            | D   | -     | -        | -         |
| BLZ                           | I   | -     | -        | -         |
| Bank                          | I   | -     | -        | -         |
| Bankkonto                     | A   | 20    | -        | -         |
| BankIBAN                      | A   | 28    | -        | -         |
| BankInhaber                   | A   | 300   | -        | -         |
| BankInfo                      | A   | 300   | -        | -         |
| BankBemerkung                 | A   | 300   | -        | -         |
| Bank2                         | I   | -     | -        | -         |
| Bank2konto                    | A   | 20    | -        | -         |
| Bank2IBAN                     | A   | 28    | -        | -         |
| Bank2Inhaber                  | A   | 300   | -        | -         |
| Bank2Info                     | A   | 300   | -        | -         |
| Bank2Bemerkung                | A   | 300   | -        | -         |
| Rechnung1Name1                | A   | 100   | -        | -         |
| Rechnung1Name2                | A   | 100   | -        | -         |
| Rechnung1Strasse              | A   | 100   | -        | -         |
| Rechnung1Adresszusatz         | A   | 200   | -        | -         |
| Rechnung1Land                 | A   | 3     | -        | -         |
| Rechnung1PLZ                  | A   | 10    | -        | -         |
| Rechnung1Ort                  | A   | 100   | -        | -         |
| Rechnung1Ortsteil             | A   | 100   | -        | -         |
| Rechnung1Adressgebiet         | A   | 300   | -        | -         |
