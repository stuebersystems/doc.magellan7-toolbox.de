# Importieren mit dem Importassistenten

Der Importassistent kann im MAGELLAN-Administrator in der Ansicht ```Datenimporte``` über ```Daten über MAGELLAN-Importformat importieren``` aufgerufen werden. Der Import über das MAGELLAN-Importformat dient dem einmaligen Importieren von Daten nach MAGELLAN.

##Voraussetzungen
Es gelten folgende Voraussetzungen für den Import der Dateien:

1. Die Dateien müssen den im vorherigen Abschnitt beschriebenen Formaten entsprechen.
2. In MAGELLAN muss mindestens ein Mandant angelegt sein.
3. Bei Import von zeitraumbezogenen Daten (Klassen, Schüler-Laufbahn und Schüler-Fachdaten) müssen entsprechend der Importdaten in den Dateien die Zeiträume in MAGELLAN angelegt sein.

##Schritt 1: Importieren der Schlüsselverzeichnisse

![Abbildung 1: Hinweis zum Importieren der Schlüssel](/assets/images/importe/magimp-1.png)

Es ist sehr wichtig, dass Sie vor dem Erstimport die Schlüsselverzeichnisse Ihres Bundeslandes importieren. Schlüsselverzeichnisse stellen Stammdaten dar, die in MAGELLAN oftmals über Dropdown-Comboboxen in den jeweiligen Masken ausgewählt werden. Zum einen dienen Sie zur Auswahl vieler Daten bei der allgemeinen Arbeit im Schulalltag, zum anderen werden die von uns vorgegebenen Schlüsselverzeichnisse von Ihnen zur Erstellung der Landesstatistiken oder für Berechnungsskripte und zum Ausdruck von Zeugnissen benötigt, je nachdem um welches Schlüsselverzeichnis es sich handelt und in welchem Bundesland Sie arbeiten. Wie Sie die Schlüsselverzeichnisse für Ihr Bundesland importieren, lesen Sie bitte in der Dokumentation [MAGELLAN 6](https://doc.magellan6.stueber.de/). 

##Schritt 2: Auswahl der Importart
Sie haben die Möglichkeit, jede Importdatei einzeln zu importieren oder einen sogenannten Batch-Import auszuführen. Beide Methoden haben ihre Vor- und Nachteile.

### Batch-Import

Der Batch-Import stellt eine Möglichkeit dar, das Verzeichnis in dem die Importdateien liegen, anzuge-ben und den restlichen Import automatisiert durchlaufen zu lassen. Voraussetzung hierfür ist, dass die Importdateien entsprechend der Namenskonvention (z.B. schueler.import.csv) vorliegen. Der Batch-Import kann, je nach Datenmenge und Anzahl der Importdateien die Sie importieren möchten, eine gewisse Zeit in Anspruch nehmen.<br/>Die Möglichkeit der Datenprüfung ist bei einem Batch-Import nicht gegeben, da einige Daten auf andere Verweisen und die Prüfung aufgrund der fehlenden Einträge – da bei einer Prüfung nicht importiert wird – zu Fehlmeldungen führen würde.<br/>Wenn Sie sich sicher sind, dass Ihre Importdateien korrekt sind, oder den Import einfach mal austesten möchten und entsprechend **Sicherungen** ihrer MAGELLAN Datenbank gemacht haben, können Sie den Batch-Import nutzen.

### Single-Import

Beim Single-Import wählen Sie eine zu importierende Importformatdatei aus und geben in einem weiteren Schritt an, welche Daten diese Importdatei beinhalten. Wenn Sie die Namenskonvention wie zuvor angegeben (z.B. schueler.import.csv) benutzen, erkennt der Importassistent anhand des Namens, dass es sich um zu importierende Schüler-Stammdaten handelt. Beachten Sie dabei bitte die Importreihenfolge.

![Abbildung 3: Auswahl der Importart](/assets/images/importe/magimp-2.png)

##Schritt 3: Auswahl der Importdaten

In der Auswahl der Importdaten erhalten Sie einen Überblick welche Daten nach MAGELLAN importiert werden könnten. Im oberen Abschnitt befinden sich Stammdaten, die Sie in wahlloser Reihenfolge importieren können und nicht aufeinander aufbauen. 

![Abbildung 4: Auswahl der Importdaten](/assets/images/importe/magimp-3.png)

Im unteren Bereich befinden sich Importdaten, die aufeinander aufbauen, entweder auf Daten, die sich im oberen Bereich befinden oder auf Daten, die sich im gleichen Bereich befinden. Die Reihenfolge der Anordnung gibt auch bereits Auskunft über die empfohlene Importreihenfolge.<br/>
Eine Besonderheit stellen hier Medien und Medienexemplare dar. Medienexemplare erfordern den vorigen Import der Medien, aber keiner weiteren Daten.<br/>Wenn die Importdatei der Namenskonvention entspricht (z.B. betriebe.import.csv), dann erkennt der Importassistent am Namen um welche Importdaten es sich handelt und wählt für Sie entsprechend vor

##Schritt 4: Auswahl der Importparameter

![Abbildung 5: Auswahl der Importparameter](/assets/images/importe/magimp-4.png)

Für alle Importe muss der Mandant ausgewählt werden, in den die Daten importiert werden sollen. Bei Medienexemplaren geben Sie zusätzlich an, in welchen Medienkatalog die Exemplare gehören. Wenn Sie Medienexemplare haben, die in verschiedene Kataloge importiert werden sollen, müssen Sie die Daten pro Medienkatalog in eine Importdatei legen einzeln importieren und jeweils den Medienkatalog angeben.

##Schritt 5: Übersicht und Datenprüfung

Dies ist der letzte Schritt vor dem eigentlichen Import. Sie können hier nachlesen, welche Daten Sie für den Import ausgewählt haben und ob Sie eine reine Prüfung der Daten ohne Import wünschen. Klicken Sie auf ```Fertigstellen```, um den Import oder die Prüfung zu starten.

![Abbildung 6: Übersicht und Datenprüfung](/assets/images/importe/magimp-5.png)

##Schritt 6: Prüfung oder Import der Daten durchführen

Während der Datenprüfung oder des Imports wird eine Liste mit Hinweisen gefüllt, wenn Daten nicht importiert werden können. Wenn es sich um kritische Probleme handelt, kann es sein, dass der Import mit entsprechenden Meldungen komplett abbricht.

In den meisten Fällen meldet der Importassistent die Datensätze oder Felder, die nicht importiert werden können mit einer Begründung in den Hinweisen und setzt den Prüf- oder Importvorgang fort.

Sie können entscheiden, den Vorgang manuell sofort abzubrechen und den Hinweisen nachzugehen, oder den Vorgang durchlaufen zu lassen und am Ende alle Meldungen zu untersuchen. Dazu können Sie die Meldungen bequem nach Excel exportieren lassen.

Die Datenprüfung beinhaltet gegenüber der Prüfung beim Import zusätzlich folgende Prüfungsroutinen:

* Beim Import der Schulen (schulen.import.csv) Es wird geprüft, ob die Schule bereits existiert, wenn nicht, wird eine Warnung ausgegeben.

Zweck: Sie können mit dieser Prüfung vorab klären, ob Ihre zu importierenden Daten Schulen enthalten, die noch nicht vorhanden sind. Damit könnten Sie evtl. Schreibfehler bei der Schulnummer vor dem Import ausfindig machen und korrigieren.

* Alle anderen Importe


Es wird geprüft, ob ein der Datensatz mit angegebenem Wert in einer Schlüssel- oder Verweistabelle existiert. Beispiel: schüler.import.csv – Spalte „Geburtsland“ enthält den Importwert „DEU“. Es wird geprüft, ob in der Schlüsseltabelle „Staatsangehoerigkeiten“ ein Datensatz mit dem Kürzel „DEU“ existiert. Wenn nicht, dann wird eine Warnung ausgegeben und Sie haben die Möglichkeit, ggf. den Wert zu korrigieren, diesen mit vollständigen Daten in MAGELLAN einzutragen, oder einfach zu ignorieren und den Datensatz beim Import in das Schlüsselverzeichnis mit dem Kürzel importieren zu lassen (Achtung: Dadurch fehlen Ihnen Felder wie Schlüssel und Bezeichnung in der Schlüsseltabelle; Schlüssel sind für die Statistiken wichtig).

> #### warning::Wichtig!
>
> Wenn Sie nur den Import wählen, erhalten Sie diese Warnungen nicht und der Import wird inklusive dem Import aller nicht vorhandenen Datensätze in Schlüssel- und sonstigen Verweistabellen durchgeführt.

![Abbildung 7: Prüfung von zu importierenden Betriebedaten](/assets/images/importe/magimp-6.png)

In der obigen Abbildung wurden Betriebedaten für den Import geprüft. Der Importassistent hat in einem Datensatz (Zeile 1500) einen Fehler im Feld „PLZ“ gefunden. Die PLZ enthält den Wert „1976cc“ und ist damit länger als eine PLZ sein dürfte (5 Zeichen).<br/> 
Bei einem Import würde der Betriebe-Datensatz importiert werden, lediglich das Feld „PLZ“ wäre in Magellan für diesen Betrieb nicht gefüllt.

