# Schnittstellenformat schueler_schulen.import.csv

Die Importdatei kann maximal aus folgenden Feldern bestehen:

Feldname| Typ| Größe| Bemerkung
--|--|--|--
SchuelerVorname |A V P| 100|
SchuelerNachname |A V P |100|
SchuelerGeburtsdatum |D V P |10| 
SchuleKuerzel |A V P |10| Verweis auf „Schulen“ (Kuerzel)
Schulform |A V| 20 |Verweis auf das Schlüsselverzeichnis „SchulformenHerkunft“ (Kuerzel)
Schulart |A V |20| Verweis auf das Schlüsselverzeichnis „SchulartenHerkunft“ (Kuerzel)
Von |D | 10| Herkunftsschule von In der Form TT.MM.JJJJ
Bis |D  |10 |Herkunftsschule bis In der Form TT.MM.JJJJ
LetzteKlasse| A |15 |Zuletzt besuchte Klasse der Schule
Klassenleiter|A |50 |Klassenleiter der letzten Klasse
Abschluss |A V| 20| Verweis auf das Schlüsselverzeichnis „AbschluesseExtern“ (Kuerzel)
Herkunft |A V |20| Verweis auf das Schlüsselverzeichnis „Herkunftsarten“ (Kuerzel)
Unterlagen |A V |20| Verweis auf das Schlüsselverzeichnis „Herkunftsunterlagen“ (Kuerzel)
Klassenstufe |A V |20| Verweis auf das Schlüsselverzeichnis „Klassenstufen“ (Kuerzel)

## Spaltenköpfe zur Vorlage für Importdateien

Um eine Importdatei vorzubereiten, können Sie die nachfolgenden Feldnamen in Ihre Zwischenablage kopieren, zum Beispiel in eine Exceltabelle einfügen.

### Spaltenköpfe für schueler_schulen.import.csv, Stand: 23.02.2021

```
"SchuelerVorname";"SchuelerNachname";"SchuelerGeburtsdatum";"SchuleKuerzel";"Schulform";"Schulart";"Von";"Bis";"LetzteKlasse";"Klassenleiter";"Abschluss";"Herkunft";"Unterlagen";"Klassenstufe"
```

!!! warning "Wichtig"

    Einige der Felder sind aktuell noch nicht zu verwenden, bitte beachten Sie die Hinweise dazu in der Beschreibung pro Feld!

### Das Ergebnis wird als senkrechte Spalte angezeigt

Kopieren Sie anschließend die Spalte mit den Feldnamen erneut, wechseln auf ein neues Tabellenblatt und fügen die Inhalte mit der Option "Transponieren" wieder ein, damit werden die Inhalte der Zwischenablage statt senkrecht waagerecht eingefügt.

![Ändern Sie beim Einfügen die Anzeigerichtung](/assets/images/importe/magimp-8.png)

### Das Ergebnis wird waagerecht, aber nicht in Spalten angezeigt

Wechseln Sie auf `Daten > Text in Spalten`. Bestätigen Sie als erstes, dass die Inhalte `getrennt` dargestellt werden sollen, wählen Sie auf der nächsten Karte als Trennzeichen bitte das ``Semikolon`` aus.

![Teilen Sie die Werte auf Spalten auf](/assets/images/importe/magimp-9.png)
