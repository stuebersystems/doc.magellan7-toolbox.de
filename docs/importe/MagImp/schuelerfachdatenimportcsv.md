# Schnittstellenformat schueler_fachdaten.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname |Typ |Größe |Bemerkung
--|--|--|--
SchuelerIDExtern| I P||  Derzeit bitte nicht verwenden
SchuelerVorname| A V P |30|-
SchuelerNachname| A V P |50|-
SchuelerGeburtsdatum| D V P |10| In der Form TT.MM.JJJJ
KlasseIDExtern| I V P|  |Derzeit bitte nicht verwenden
KlasseKuerzel| A V P |10 |Verweis auf „Klassen“ (Kuerzel)
ZeitraumVon |D P| 10 |In der Form TT.MM.JJJJ
ZeitraumBis |D P |10 |In der Form TT.MM.JJJJ
Halbjahr |S P||  1,2,3 oder 4
FachIDExtern |I V P || Derzeit bitte nicht verwenden
FachKuerzel |A V P |10| Verweis auf „Faecher“ (Kuerzel)
Fachstatus |A V |10| Verweis auf „Faechstati“ (Kuerzel)
Unterrichtsart|A V |10| Verweis auf das Schlüsselverzeichnis „Unterrichtsarten“ (Kuerzel)
Schwerpunkt |A V |10| Verweis auf das Schlüsselverzeichnis „Fachschwerpunkte“ (Kuerzel)
Niveau| A V |10 |Verweis auf das Schlüsselverzeichnis „FachNiveaus“ (Kuerzel)
Kursnr| S|| -
Beurteilung |M| 255 |-
Endnote1 |N| |-
Endnote2 |N| |-
Notenart |A| 1| Mögliche Werte:<br/>N = Notenwert<br/>P = Punktwert<br/>F = Füllwert<br/>Ist Voraussetzung, wenn Noten mit importiert werden sollen.
Faktor| S|| -
Merkmal| A| 8| -
LehrerIDExtern |I V | |Derzeit bitte nicht verwenden
LehrerKuerzel |A V |10| Verweis auf „Lehrer“ (Kuerzel)

## Erläuterungen zu den Zeitraum- und Halbjahr- Feldern

Die Zeitraumfelder „ZeitraumVon“ und „ZeitraumBis“ erstrecken sich über ein Schuljahr vom 01.08.XXXX – 31.07.XXXX. Das Feld „Halbjahr“ bestimmt um welches Halbjahr es sich handelt.
Damit lassen sich auch mehrjährige Klassen in Berufsbildenden Schulen abbilden, indem das Halbjahr sich jeweils um eins erhöht.

Beispiel:

„ZeitraumVon“| „ZeitraumBis“ |„Halbjahr“ | Beschreibung
--|--|--|--
01.08.2018 |  31.07.2019 | 1  |(01.08.2018-31.01.2019) – 1. Halbjahr 2018/2019
01.08.2018 |  31.07.2019 | 2  |(01.02.2019-31.07.2019) – 2. Halbjahr 2018/2019
01.08.2019 |  31.07.2020 | 3   |(01.08.2019-31.01.2020) – 1. Halbjahr 2019/2020
01.08.2019 |  31.07.2020     | 4   |(01.02.2020-31.07.2020) – 2. Halbjahr 2019/2020

!!! info "Hinweis"

    Der Import ist zum einmaligen Einlesen gedacht, bestehende Schülerfachdaten werden nicht überschrieben oder aktualisiert.

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schueler_fachdaten.import.csv, Stand: 30.06.2017

SchuelerIDExtern
SchuelerVorname
SchuelerNachname
SchuelerGeburtsdatum
KlasseIDExtern
KlasseKuerzel
ZeitraumVon
ZeitraumBis
Halbjahr
FachIDExtern
FachKuerzel
Fachstatus
Unterrichtsart
Schwerpunkt
Niveau
Kursnr
Beurteilung
Endnote1
Endnote2
Notenart
Faktor
Merkmal
LehrerIDExtern
LehrerKuerzel

!!! info "Hinweis"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Leerzeichen`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
