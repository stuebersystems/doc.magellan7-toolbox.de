# Importieren mit dem Importassistenten

Der Importassistent kann im MAGELLAN-Administrator in der Ansicht `Datenaustausch` über `Daten über MAGELLAN-Importformat importieren` aufgerufen werden. Der Import über das MAGELLAN-Importformat dient dem einmaligen Importieren von Daten nach MAGELLAN.

## Voraussetzungen

Es gelten folgende Voraussetzungen für den Import der Dateien:

1. Die Dateien müssen den im vorherigen Abschnitt beschriebenen Formaten entsprechen.
2. In MAGELLAN muss mindestens ein Mandant angelegt sein.
3. Bei Import von zeitraumbezogenen Daten (Klassen, Schüler-Laufbahn und Schüler-Fachdaten) müssen entsprechend der Importdaten in den Dateien die Zeiträume in MAGELLAN angelegt sein.

## Importieren der Schlüsselverzeichnisse

Es ist sehr wichtig, dass Sie vor dem Erstimport die Schlüsselverzeichnisse Ihres Bundeslandes importieren. Schlüsselverzeichnisse stellen Stammdaten dar, die in MAGELLAN oftmals über Dropdown-Comboboxen in den jeweiligen Masken ausgewählt werden. Zum einen dienen Sie zur Auswahl vieler Daten bei der allgemeinen Arbeit im Schulalltag, zum anderen werden die von uns vorgegebenen Schlüsselverzeichnisse von Ihnen zur Erstellung der Landesstatistiken oder für Berechnungsskripte und zum Ausdruck von Zeugnissen benötigt, je nachdem um welches Schlüsselverzeichnis es sich handelt und in welchem Bundesland Sie arbeiten. Wie Sie die Schlüsselverzeichnisse für Ihr Bundesland importieren, lesen Sie bitte in der Dokumentation [Datenaustausch > Kataloge (Schlüsselverzeichnisse) importieren](https://doc.magellan7.stueber.de/schulverwaltung/admin/datenaustausch/#kataloge-schlusselverzeichnisse-importieren).

## Der Import

!!! warning "Wichtig"

    Die nachstehende Beschreibung setzt mindestens die MAGELLAN-Ausgabe 7.1.4 voraus.

### Vorbereitung

Bereiten Sie Ihre einzulesenden Daten bitte entsprechend unserer Beschreibung im [MAGELLAN-Importformat](https://doc.magellan7-toolbox.stueber.de/importe/) vor.

!!! tip "Tipp"

    Sie können den Dateinamen der *.csv-Dateien frei wählen, es ist aber sinnvoll die vorgeschlagenen Namen je Importdatei zu verwenden, der Assistent erkennt die Namen und sortiert diese automatisch in die inhaltlich aufeinander aufbauende Reihenfolge.

Empfohlener Dateiname|Beschreibung
--|--
schulen.import.csv | Enthält die Stammdaten der Schulen
betriebe.import.csv | Enthält die Stammdaten der Betriebe
lehrer.import.csv | Enthält die Stammdaten der Lehrer
schueler.import.csv | Enthält die Stammdaten der Schüler und Bewerber
sorgebe.import.csv | Enthält die Stammdaten der Sorgeberechtigten
verlage.import.csv | Enthält die Stammdaten der Verlage
lieferanten.import.csv | Enthält die Stammdaten der Lieferanten
medien.import.csv | Enthält die Stammdaten der Medien
exemplare.import.csv | Enthält die Exemplardaten zu den Medien
klassen.import.csv | Enthält die Stamm- und Zeitraumdaten der Klassen
schueler_laufbahn.import.csv | Enthält die Laufbahndaten der Schüler
schueler_fachdaten.import.csv | Enthält die Fachdaten der Schüler
schueler_sorgebe.import.csv | Enthält die Zuordnung der Sorgeberechtigten zu den Schülern
schueler_schulen.import.csv | Enthält die bereits besuchten Schulen der Schüler (Stichwort: Herkunftsschulen)
schueler_ausbildung.import.csv | Enthält die Ausbildungsdaten der Schüler

### Einlesen oder Prüfen der Daten

Ihre Dateien können im Modul MAGELLAN ADMINISTRATOR im Punkt `Datenaustausch > Daten über das MAGELLAN Importformat importieren` eingelesen werden. Starten Sie den Assistenten per Doppelklick auf den Bereich.

|So gehen Sie vor:|
|--|
|**Importformatdatei wählen**<br/><br/>Klicken Sie auf das `Plus`-Symbol und verweisen auf eine oder mehrere zu importierende csv-Dateien. Erkennt der Assistent die Dateinamen, ordnet er in der ersten Spalte `Importart` die entsprechende Bezeichnung zu. Ist der Dateiname nicht zuzuordnen, erhält die Zeile den Wert `unbekannt`, die Schaltfläche `Weiter` bleibt in diesem Fall deaktiviert. Bitte ordnen Sie in diesem Fall die korrekte Auswahl zu. <br/>Sobald Sie die Auswahl vollständig getroffen haben, sortiert der Assistent die Dateien in die korrekte Reihenfolge für das Einlesen, die `Weiter`-Schaltfläche wird aktiviert.<br/>Eine versehentlich ausgewählte Datei können Sie über das `Minus`-Symbol wieder entfernen.<br/>Klicken Sie auf `Weiter`!|
|**Abbildung:**<br/><img src="/assets/images/importe/import01.png">|
|**Auswahl der Importparameter**<br/><br/>Wählen Sie bitte Ihren Zielmandanten im Feld `Importiere für den folgenden Mandanten` aus!<br/><br/>Je nach Dateiauswahl (Medien-Exemplare) auf der vorangegangenen Karte, kann das Feld `Importiere für den folgenden Medienkatalog` gezeigt werden, treffen Sie hier bitte Ihre Auswahl!<br/><br/>**Datenprüfung und Import**<br/><br/>Setzen Sie den Haken um Ihre gewählten Dateien im Anschluss prüfen zu lassen. Ist der Haken nicht aktiviert, wird versucht die Daten in Ihre Datenbank einzulesen.<br/>Treffen Sie Ihre Auswahl und klicken bitte auf `Weiter`!|
|**Abbildung:**<br/><img src="/assets/images/importe/import02.png">|
|Klicken Sie auf `Fertigstellen`! <br/>Das Einlesen oder Prüfen, je nach Ihrer Auswahl auf der vorangegangenen Seite, geschieht dateiweise. Es werden im Fenster die Meldungen des Einlesens oder des Prüfens für die Dateien gezeigt. Im Anschluss erscheint ein Fenster, in dem Sie entscheiden können, die nächste Datei einlesen oder prüfen zu lassen. Die eventuell zuvor ausgegebenen Meldungen bleiben in der Liste bestehen und werden ggfs. durch weitere Meldungen ergänzt.<br/>Entstandene Meldungen können Sie exportieren.<br/>Nach Abschluss der Prüfung oder des Einlesens schließen Sie den Assistenten.|
|**Abbildung:**<br/><img src="/assets/images/importe/import03.png">|

## Fehlermeldungen

Während der Datenprüfung oder des Imports wird eine Liste mit Hinweisen gefüllt, wenn Daten nicht importiert werden können. Wenn es sich um kritische Probleme handelt, kann es sein, dass der Import mit entsprechenden Meldungen komplett abbricht.

In den meisten Fällen meldet der Importassistent die Datensätze oder Felder, die nicht importiert werden können mit einer Begründung in den Hinweisen und setzt den Prüf- oder Importvorgang fort.

Sie können entscheiden, den Vorgang manuell sofort abzubrechen und den Hinweisen nachzugehen, oder den Vorgang durchlaufen zu lassen und am Ende alle Meldungen zu untersuchen. Dazu können Sie die Meldungen bequem nach Excel exportieren lassen.

Die Datenprüfung beinhaltet gegenüber der Prüfung beim Import zusätzlich folgende Prüfungsroutinen:

* Beim Import der Schulen (schulen.import.csv) Es wird geprüft, ob die Schule bereits existiert, wenn nicht, wird eine Warnung ausgegeben.

Zweck: Sie können mit dieser Prüfung vorab klären, ob Ihre zu importierenden Daten Schulen enthalten, die noch nicht vorhanden sind. Damit könnten Sie evtl. Schreibfehler bei der Schulnummer vor dem Import ausfindig machen und korrigieren.

* Alle anderen Importe

Es wird geprüft, ob ein der Datensatz mit angegebenem Wert in einer Schlüssel- oder Verweistabelle existiert. Beispiel: schüler.import.csv – Spalte „Geburtsland“ enthält den Importwert „DEU“. Es wird geprüft, ob in der Schlüsseltabelle „Staatsangehoerigkeiten“ ein Datensatz mit dem Kürzel „DEU“ existiert. Wenn nicht, dann wird eine Warnung ausgegeben und Sie haben die Möglichkeit, ggf. den Wert zu korrigieren, diesen mit vollständigen Daten in MAGELLAN einzutragen, oder einfach zu ignorieren und den Datensatz beim Import in das Schlüsselverzeichnis mit dem Kürzel importieren zu lassen (Achtung: Dadurch fehlen Ihnen Felder wie Schlüssel und Bezeichnung in der Schlüsseltabelle; Schlüssel sind für die Statistiken wichtig).

!!! warning "Wichtig"

    Wenn Sie nur den Import wählen, erhalten Sie diese Warnungen nicht und der Import wird inklusive dem Import aller nicht vorhandenen Datensätze in Schlüssel- und sonstigen Verweistabellen durchgeführt.

![Abbildung 7: Prüfung von zu importierenden Betriebedaten](/assets/images/importe/magimp-6.png)

In der obigen Abbildung wurden Betriebedaten für den Import geprüft. Der Importassistent hat in einem Datensatz (Zeile 1500) einen Fehler im Feld „PLZ“ gefunden. Die PLZ enthält den Wert „1976cc“ und ist damit länger als eine PLZ sein dürfte (5 Zeichen).

Bei einem Import würde der Betriebe-Datensatz importiert werden, lediglich das Feld „PLZ“ wäre in Magellan für diesen Betrieb nicht gefüllt.
