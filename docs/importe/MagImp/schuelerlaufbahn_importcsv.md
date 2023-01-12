
# Schnittstellenformat schueler_laufbahn.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname |Typ |Größe |Bemerkung
--|--|--|--
SchuelerVorname |A P |100|-
SchuelerNachname |A P |100|-
SchuelerGeburtsdatum| D P |10| In der Form TT.MM.JJJJ
KlasseKuerzel |A V P |10 |Verweis auf „Klassen“ (Kuerzel)
ZeitraumVon |D P |10 |In der Form TT.MM.JJJJ (bitte Hinweis unten lesen, das Datum ist immer der Start des Schuljahres)
ZeitraumBis |D P |10 |In der Form TT.MM.JJJJ (bitte Hinweis unten lesen, das Datum ist immer das Ende des Schuljahres)
Halbjahr |S P | | 1 oder 2 (bitte Hinweis unten lesen!)
Gewechselt |A P |1 |Mögliche Werte:<br/>+ = Historischer Schülerzeitraum<br/>J  = Historischer Schülerzeitraum (Im gleichen Zeitraum die Klasse gewechselt)<br/>N = Aktueller Schülerzeitraum
Wiederholer |L P|  |Mögliche Werte:<br/>J  = Ja, Wiederholer<br/>N = Nein, kein Wiederholer
Ueberspringer |L P|  |Mögliche Werte:<br/>J  = Ja, Überspringer<br/>N = Nein, kein Überspringer
Fehlstunden |N P|  |-
FehlstundenU |N P|  |-
Zugang |D |10 |Zugang zur Klasse
Abgang |D |10 |Abgang von der Klasse
Versetzt |L||-|  
Versetzungsart |A V |20 |Verweis auf das Schlüsselverzeichnis „Versetzungsarten“ (Kuerzel)
Wiederholungsart|A |20 |Verweis auf das Schlüsselverzeichnis „Wiederholungsarten“ (Kuerzel)
VersetztAm |D |10 |In der Form TT.MM.JJJJ
SchulformEintritt|D |10 |In der Form TT.MM.JJJJ
Aufnahmepruefung |A V |20| Verweis auf das Schlüsselverzeichnis „Aufnahmepruefungen“ (Kuerzel)
AufnahmepruefungBestanden |L|-|-|  
Nachpruefung |A| 10| Verweis auf das Schlüsselverzeichnis „Nachpruefungen“ (Kuerzel)
NachpruefungBestanden| L||-|  
Empfehlung |A V |20| Verweis auf das Schlüsselverzeichnis „Empfehlungen“ (Kuerzel)
Elternwunsch |A V| 20| Verweis auf das Schlüsselverzeichnis „Empfehlungen“ (Kuerzel)
Abschluss1 |A V| 20| Verweis auf das Schlüsselverzeichnis „AbschluesseIntern“ (Kuerzel)
Abschluss1Art |A V| 20| Verweis auf das Schlüsselverzeichnis„Abschlussarten“ (Kuerzel)
Abschluss1Datum| D| 10| In der Form TT.MM.JJJJ
Abschluss1Note| A V| 10| Verweis auf das Schlüsselverzeichnis „Noten“ (Kuerzel)
Abschluss2 |A V| 20| Verweis auf das Schlüsselverzeichnis „AbschluesseIntern“ (Kuerzel)
Abschluss2Art| A V| 20| Verweis auf das Schlüsselverzeichnis „Abschlussarten“ (Kuerzel)
Abschluss2Datum| D| 10| In der Form TT.MM.JJJJ
Abschluss2Note |A V| 10| Verweis auf das Schlüsselverzeichnis „Noten“ (Kuerzel)
TutorKuerzel |A V |6| Verweis auf „Lehrer“ (Kuerzel)
ZeugniskonferenzAm| D |10| In der Form TT.MM.JJJJ
ZeugnisausgabeAm| D |10| In der Form TT.MM.JJJJ

## Erläuterungen zu den Zeitraum- und Halbjahr- Feldern

Die Zeitraumfelder „ZeitraumVon“ und „ZeitraumBis“ erstrecken sich über ein Schuljahr vom 01.08.XXXX – 31.07.XXXX. Das Feld „Halbjahr“ bestimmt um welches Halbjahr es sich handelt.

Beispiel:

„ZeitraumVon“| „ZeitraumBis“ |„Halbjahr“ | Beschreibung
--|--|--|--
01.08.2016 |  31.07.2017 | 1  |(01.08.2010-31.01.2011) – 1. Halbjahr 2010/2011
01.08.2016 |  31.07.2017 | 2  |(01.02.2011-31.07.2011) – 2. Halbjahr 2010/2011

!!! info "Hinweis"

    Der Import ist zum einmaligen Einlesen gedacht, bestehende Daten werden nicht überschrieben oder aktualisiert.

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schueler_laufbahn.import.csv, Stand: 23.02.2021

```
"SchuelerVorname";"SchuelerNachname";"SchuelerGeburtsdatum";"KlasseKuerzel";"ZeitraumVon";"ZeitraumBis";"Halbjahr";"Gewechselt";"Wiederholer";"Ueberspringer";"Fehlstunden";"FehlstundenU";"Zugang";"Abgang";"Versetzt";"Versetzungsart";"Wiederholungsart";"VersetztAm";"SchulformEintritt";"Aufnahmepruefung";"AufnahmepruefungBestanden";"nachpruefung";"NachpruefungBestanden";"Empfehlung";"Elternwunsch";"Abschluss1";"Abschluss1Art";"Abschluss1Datum";"Abschluss1Note";"Abschluss2";"Abschluss2Art";"Abschluss2Datum";"Abschluss2Note";"TutorKuerzel";"ZeugniskonferenzAm";"ZeugnisausgabeAm"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
