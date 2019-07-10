# Die Skriptkategorien

Skripte können in MAGELLAN nicht an beliebiger Stelle ausgeführt werden, sie werden stets in bestimmten Situationen genutzt.

Die Skripte in MAGELLAN kann man daher gut in Kategorien zusammenfassen:

[Kategorie „Administration“](#Kategorie Administration)

[Kategorie Schülerbewegungen](#Kategorie Schülerbewegungen)

[Kategorie "Datenabgleich"](#Kategorie Datenabgleich)

[Kategorie „Verordnungen“](#Kategorie Verordnungen)

## Kategorie „Administration“

Die Kategorie „Administration“ umfasst alle Skripte, die aus dem MAGELLAN-Administrator heraus aufgerufen werden können.
-|Skripte der Kategorie „Administration“
-|-
Skriptname |**Datenbank löschen.dws**
Beschreibung |Dieses Skript löscht den Inhalt der aktuellen MAGELLAN-Datenbank. Auf Wunsch können die Schlüsselverzeichnisse und/oder das Postleitzahlverzeichnis davon ausgenommen werden.
Skriptname |**Importiere Schlüssel.dws**
Beschreibung| Dieses Skript importiert die Schlüsselverzeichnisse des bei der Installation ausgewählten Bundeslandes/Landes in die aktuelle MAGELLAN-Datenbank. Es wird dabei zwischen allgemeinbildenden und berufsbildenden Schlüsseln unterschieden.
Skriptname |**Importiere PLZ.dws**
Beschreibung |Dieses Skript importiert das Postleitzahlverzeichnis in die aktuelle MAGELLAN-Datenbank. Dieser Import beinhaltet auch die Schlüsselverzeichnisse für Gemein-den, Regierungsbezirke, Kreise und Bundesländer.
Skriptname |**Exportiere PLZ.dws**
Beschreibung |Dieses Skript exportiert das Postleitzahlverzeichnis der aktuellen MAGELLAN-Datenbank. Dieser Export beinhaltet auch die Schlüsselverzeichnisse für Gemeinden, Regierungsbezirke, Kreise und Bundesländer.
Skriptname |**Benutzerrechte zuweisen.dws**
Beschreibung |Dieses Skript wird beim Anlegen oder Ändern von Benutzerrechten durchlaufen.
Skriptname |**Synchronisiere Zugriffsrechte.dws**
Beschreibung |Dieses Skript wird beim Synchronisieren der Benutzerrechte durchlaufen.

## Kategorie „Schülerbewegungen“

Die Kategorie „Schülerbewegungen“ umfasst alle Skripte, die eingesetzt werden, um Schüler einzuschu-len, auszuschulen oder von einer Klasse in die nächste zu verschieben.

-|Skripte der Kategorie „Schülerbewegung“
-|-
Skriptname | **Schüler einschulen.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler einschulen“ aufgerufen
Skriptname |**Schüler fortschreiben.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler fortschreiben“ aufgerufen
Skriptname |**Schüler versetzen.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler versetzen“ aufgerufen
Skriptname |**Schüler wechseln.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler wechseln“ aufgerufen
Skriptname| **Schüler korrigieren.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler korrigieren“ aufgerufen
Skriptname |**Schüler ausschulen.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler ausschulen“ aufgerufen
Skriptname |**Schüler rückversetzen.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Schüler rückversetzen“ aufgerufen

## Kategorie „Datenabgleich“

Die Kategorie „Datenabgleich“ umfasst alle Skripte, die zum Abgleich von Daten zwischen MAGELLAN und daVinci, zwischen MAGELLAN und dem MAGELLAN Data Warehouse oder einfach nur zwischen Tabellen innerhalb von MAGELLAN benötigt werden.

-| Skripte derKategorie „Datenabgleich“
-|-
Skriptname |**Importiere SDTF.dws**
Beschreibung |Dieses Skript wird beim Import einer Schuldatentransferdatei nach MAGELLAN im Programm für den MAGELLAN-Datenaustausch (MagSDTFSync.exe) aufgerufen
Skriptname| **Exportiere SDTF.dws**
Beschreibung |Dieses Skript wird beim Export einer Schuldatentransferdatei aus MAGELLAN im Programm für den MAGELLAN-Datenaustausch (MagSDTFSync.exe) aufgerufen
Skriptname |**Exportiere Fachwahl Schueler.dws**
Beschreibung |Dieses Skript wird beim Durchlaufen des Dialogfensters „Fachwahl exportieren“ in unter „Ansicht Abitur > Fachwahl“ aufgerufen
Skriptname| **Synchronisiere ABI.dws**
Beschreibung |Dieses Skript wird beim Synchronisieren von Schülerdaten in die Ansicht „Abitur“ aufgerufen Synchronisiere BBS.dws Dieses Skript wird beim Synchronisieren von Schülerdaten in die Ansicht „Berufsschule“ aufgerufen

## Kategorie „Verordnungen

Die Kategorie „Verordnungen“ umfasst alle Skripte, die eine Berechnungsverordnung definieren. Hierzu zählen Versetzungsordnungen, Abiturverordnungen und Notenberechnungen. Die Skripte dieser Kategorie unterscheiden sich von anderen Skripten dahingehend, dass Sie nicht direkt sondern über das Schlüsselverzeichnis „Verordnungen“ eingebunden werden.
So gibt es beispielsweise nicht ein einziges Skript für die Abiturverordnung, sondern mehrere pro Bundesland. Dabei kann es sogar innerhalb eines Bundeslandes wiederum mehrere Skripte geben, da sich bekanntlich die Verordnungen über die Zeit hinweg verändern und der eine Teil der Schüler noch nach der alten Verordnung das Abitur macht, während der andere Teil bereits an die neue Verordnung gebunden ist.
Weitere Informationen zum Schlüsselverzeichnis „Verordnungen“ finden Sie im MAGELLAN-Benutzerhandbuch.

!!! info "Hinweis"

    Eine Übersicht über alle Berechnungs- und Fachwahlskripte finden Sie in der Dokumentation Landesanpassungen unter  [http://doc.la.stueber.de/](http://doc.la.stueber.de/)  im Abschnitt [Alle Skripte im Überblick](https://doc.la.stueber.de/skriptueberblick/).       

Beschreibung des Skriptnamens: [Land] APO [Jahr].dwsSkripte mit derartigen Dateinamen definieren eine Abiturverordnung für ein bestimmtes Bundesland. Die Jahreszahl entspricht dem Veröffentlichungsjahr der Verordnung.

Skripte der Kategorie „Verordnungen“

Titel|Inhalt
--|--
|**[Land] APO [Jahr].dws** | Skripte mit derartigen Dateinamen definieren eine Abiturverordnung für ein bestimmtes Bundesland. Die Jahreszahl entspricht dem Veröffentlichungsjahr der Verordnung.
**[Land] APO-FW [Jahr].dws** | Skripte mit derartigen Dateinamen definieren eine Fachwahlverordnung für ein bestimmtes Bundesland. Die Jahreszahl entspricht dem Veröffentlichungsjahr der Verordnung.
