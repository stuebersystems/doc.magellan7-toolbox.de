# Änderungen der Datenstruktur von MAGELLAN 7 auf MAGELLAN 8

## Legende

**T** = Tabelle
**A** = Ansicht

## Neue Tabellen

Art | Name                   | Beschreibung
--- | ---------------------- | ------------
T   | Besonderheiten         | Ein Schlüsselverzeichnis zum Speichern von Besonderheiten (Text unbestimmter Länger) für Schüler oder Klasse
T   | SchuelerBesonderheiten | Verwaltet eine Liste von Besonderheiten für einen Schüler. Besonderheiten können entweder aus dem SChlüsselverzeichnis kopiert oder frei eingetragen werden
T   | KlassenBesonderheiten  | Verwaltet eine Liste von Besonderheiten für eine Klasse. Besonderheiten können entweder aus dem Schlüsselverzeichnis kopiert oder frei eingetragen werden

## Neue Felder

Art | Name                   | Feldname          | Verweis auf      | Typ | Grösse | Position
--- | ---------------------- | ----------------- | ---------------- | --- | ------ | --------
T   | SchuelerSorgebe        | Hauptversicherter |                  | L   |        | POSITION 11
A   | SchuelerFamilie        | Hauptversicherter |                  | L   |        | POSITION 6
T   | Schueler               | MerkmalA7         | SchuelerMerkmale | A   | 20     | POSITION 203
T   | Schueler               | MerkmalA8         | SchuelerMerkmale | A   | 20     | POSITION 204
T   | Schueler               | MerkmalA9         | SchuelerMerkmale | A   | 20     | POSITION 205
T   | Schueler               | MerkmalA10        | SchuelerMerkmale | A   | 20     | POSITION 206
A   | Schueler               | MerkmalA7         |                  |     |        |
A   | Schueler               | MerkmalA8         |                  |     |        |
A   | Schueler               | MerkmalA9         |                  |     |        |
A   | Schueler               | MerkmalA10        |                  |     |        |
T   | SchuelerFachdaten      | Thema             |                  | M   |        | POSITION 13
T   | BetriebeKontakte       | Anrede            |                  | A   | 1      | POSITION 7
T   | Zeugnisbemerkungen     | Fortschreiben     |                  | L   | 1      |
T   | Staatsangehoerigkeiten | Bezeichnung2      |                  | A   | 300    | POSITION 5


## Änderung von Feldern

Art | Name               | Feldname           | Änderung
--- | ------------------ | ------------------ | --------
T   | SchuelerABI        | LernleistungThema  | Feldgröße erweitert: 300
T   | SchuelerABI        | ProjektThema       | Feldgröße erweitert: 300
T   | SchuelerABI        | PraesentationThema | Feldgröße erweitert: 300
