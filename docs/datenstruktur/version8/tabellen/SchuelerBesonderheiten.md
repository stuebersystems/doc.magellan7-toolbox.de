# Tabelle SchuelerBesonderheiten

Feldname     | Typ | Größe | Funktion | Bemerkung
------------ | --- | ----- | -------- | ---------
Mandant      | I   | -     | PV       | Verweis auf Tabelle **Mandanten**
ID           | I+  | -     | P        | -
Schueler     | I   | -     | V        | Verweis auf Tabelle **Schueler**
Besonderheit | I   | -     | V        | Verweis auf Tabelle **Besonderheiten**
Kategorie    | A   | 100   | -        | -
ErfasstAm    | DT  | -     | -        | -
ErfasstVon   | A   | 300   | -        | -
Beschreibung | M   | -     | -        | -
GueltigVon   | DT  | -     | -        | -
GueltigBis   | DT  | -     | -        | -

> #### success::Hinweis
> 
>In dieser Tabelle werden die Werte aus der Schülerbemerkungsliste und der Besonderheitenliste aus `Schüler > Merkmale` gespeichert. Die Besonderheiten haben als Filterkriterium einen Wert aus dem Schlüsselverzeichnis [`Besonderheiten`](https://doc.magellan7-toolbox.stueber.de/datenstruktur/version8/schluesseltabellen/besonderheiten/)zugeordnet, für Bemerkungen ist dieses Feld immer leer.
