# Einführung

Dieses Dokuments erläutert die Magellan Scripting-Technologie. Hier finden Sie die Informationen, die Sie benötigen, wenn Sie selbst Skripte schreiben möchten.

Zwar wird die Scripting-Technologie in Magellan sehr intensiv genutzt, aber auch DaVinci verwendet für die Fachwahlüberprüfung und für einige Datenexporte und Datenimporte die gleiche Scripting-Technologie. Daher sprechen wir in diesem Dokument in der Regel von Magellan-Skripten, es sei denn wir erwähnen explizit DaVinci-Skripte.

Dieses Dokument gliedert sich wie folgt:

Kapitel |Inhalt
--|--
[Kapitel „Skripteditor“](skripteditor.md)|Beschreibt die Funktionen des Magellan- Skripteditors.
[Kapitel „Skriptsprache“](skriptsprache.md)|Beschreibt die Skriptsprache und ihre Syntax.
[Kapitel „Bibliotheken“](bibliotheken.md)|Beschreibt die zur Verfügung stehenden Funktionsbibliotheken für den Zugriff auf Datenbanken, Textdateien oder das Ausgabefenster.
[Kapitel „Änderungen“](aenderungen.md)|Beschreibt durch Versionsupdates bedingte Änderungen.

!!!info "Hinweis"

    Lesen Sie die Kapitel dieses Handbuchs sorgfältig. Oft gibt es mehrere alternative Vorgehensweisen, die zum gleichen Ziel führen. In diesem Handbuch werden Grundkenntnisse im Umgang mit Windows vorausgesetzt.

Die Magellan Scripting-Technologie ist unsere Antwort auf die unterschiedlichen landes-, verordnungs- und schulartspezifischen Anforderungen, die an eine Schulverwaltungssoftware für alle Schularten und Länder gestellt wird.

Auch DaVinci verwendet für die Fachwahlüberprüfung und für Datenaus-tausche die Magellan Scripting-Technologie.

Die Idee dabei ist es, Teile von Magellan bzw. DaVinci in Form von Skripten auszulagern und damit offen und transparent zu gestalten. Jeder Benutzer kann den Inhalt der Skripte begutachten und bekommt damit eine exakte Vorstellung, wie wesentliche Funktionen in Magellan ablaufen. Und nicht nur das:

Sie können sogar eigene Änderungen oder Korrekturen an den Skripten vornehmen, im Extremfall sogar das ganze Skript gegen eine eigene Variante austauschen.

Das klassische Beispiel stellen die Notenberechnungen im Abitur oder in der Berufsschule dar. Hier gibt es zum Teil Spezialfälle, wo die Berechnung von der Norm abweicht. Als Magellan-Nutzer gibt es da keine Einschränkungen, da Sie die Berechnungsvorschriften im Extremfall jederzeit anpassen können.

Mit der Scripting-Technologie bekommen Sie die Möglichkeit, hinter die Kulissen zu schauen. Magellan agiert nicht mehr als Black Box. Sie können die Änderungen verfolgen, die im Laufe der Zeit gemacht wer- den und Sie können, wann immer Sie wollen, selber eingreifen.

Die Magellan-Scripting-Technologie wird u.a. in folgenden Bereichen eingesetzt.

* Datenimporte und -exporte
* Prüfungsordnungen
* Versetzungsordnungen
* Notenberechnungen
* Schülerbewegungen
* Datenabgleich
