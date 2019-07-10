# Bibliotheken

Die Leistungsfähigkeit eines Scripting-Mechanismus hängt vor allem von den integrierten Funktionsbibliotheken ab. Den Skripten in MAGELLAN stehen folgende Bibliotheken zur Verfügung.

## ODBC-Bibliothek

Diese Bibliothek stellt Funktionen für den Zugriff auf ODBC zur Verfügung. ODBC steht für Open Database Connectivity und ist eine Datenbank-Middleware, die einen universellen SQL-Zugriff auf verschiedene Datenbank- und Dateisysteme ermöglicht (z.B. Excel, Access, Firebird, SQL-Server usw.).
ODBC wird in MAGELLAN vor allem für den Import und Export von Daten verwendet. So ist beispielsweise ein Import aus einer alten dBase-Schulverwaltung nach MAGELLAN problemlos möglich.

## IB-Bibliothek

Diese Bibliothek stellt die wichtigsten Zugriffsroutinen zur Verfügung, um direkt mit Firebird kommunizieren zu können. Dabei wird eine offene Datenbankverbindung von Seiten der Host-Anwendung vorausgesetzt. Das Nutzen dieser bereits vorhandenen Verbindung ermöglicht einen schnellen Zugriff auf die Datenbank, ohne dass eine separate Verbindung aufgebaut werden muss. Außerdem laufen alle Datenbankoperationen im Transaktionskontext der Host-Anwendung ab.

In MAGELLAN werden diese Funktionen überall dort verwendet, wo ausschließlich auf die MAGELLAN-Datenbank zugegriffen wird (z.B. beim Synchronisieren oder Versetzen von Schülern).

## SDTF-Bibliothek

Diese Bibliothek stellt Funktionen für den Zugriff auf SDTF-Dateien zur Verfügung. SDTF steht für  Schuldatentransferformat und ist ein textbasiertes Austauschformat für Daten aus der Schulverwaltung. Jede Textzeile stellt einen Datensatz dar, der wie folgt aufgebaut ist:

````dws
<LineType>;<Field_1>;<Field_2>;...;<Field_n>
````

In MAGELLAN wird ein Zugriff auf diese Dateien vor allem bei der Kommunikation mit daVinci gebraucht.

## OBOX-Bibliothek

Diese Bibliothek dient zur Ausgabe eines Fortschrittbalkens bzw. zur Ausgabe von Meldungen (Fehler, Warnungen, Hinweise usw.).

## Die ODBC-Bibliotheken

Die ODBC-Bibliothek stellte in früheren Zeiten Funktionen für den Zugriff auf die Datenbank über ODBC zur Verfügung. Dies sind vorallem Funktionen zum Ausführen von SQL- Anweisungen (z.B. DELETE, UPDATE, INSERT oder SELECT).

Die Implementation der Bibliothek funktioniert jetzt über eine native Verbindung, so dass ein ODBC-Treiber nicht mehr benötigt wird. Aus Kompatiblitätsgründen, wurde die Bibliothek nicht umbenannt.

Es finden sich aber Routinen zum Ermitteln von Metadaten (Tabellennamen, Feldnamen usw.) und zum Auslesen von Fehlercodes. Alle Funktionen besitzen den Präfix odbc_.

Zu beachten ist, dass je nach Datenbankgrundlage der SQL-Dialekt verschieden sein kann (SQL89, SQL92 oder SQL3). Auch unterstützt z.B. ein Client-Server-System in der Regel viel mehr SQL-Befehle als ein Desktop-System.

### ODBC-Bibliothek

Titel|Inhalt
--|--
**Funktion** | odbc_CreateAccessDB
**Syntax** | odbc_CreateAccessDB(FileName: String): Boolean;
**Beschreibung** | Erzeugt eine neue leerer Access-Datenbankdatei. Sollte diese Datei bereits existieren, dann wird sie ersetzt. Bei Erfolg liefert die Funktion TRUE zurück.
**Funktion** | odbc_ConnectToAccess
**Syntax** | function odbc_ConnectToAccess(FileName, WrkgrpFileName, UserName, Password: String): Integer;
**Beschreibung** | Stellt eine Verbindung zu einer Access-Datenbank her. Sie müssen dabei den Dateinamen der Datenbank und den Dateinamen der Arbeitsgruppendatei übergeben. Handelt es sich um eine geschützte Access-Datenbank, dann müssen Sie auch UserName und Password übergeben. Der Rückgabewert ist ein Handle auf die aktive Datenbankverbindung.
**Funktion** | odbc_ConnectToDBase
**Syntax** | function odbc_ConnectToDBase(FolderName: String): Integer;
**Beschreibung** | Stellt eine Verbindung zu einer dBase-Datenbank her. Sie müssen dabei in FolderName das Verzeichnis übergeben, indem sich die DBF-Dateien befinden. Der Rückgabewert ist ein Handle auf die aktive Datenbankverbindung.
**Funktion** | odbc_ConnectToExcel
**Syntax** | function odbc_ConnectToExcel(FileName: String): Integer;
**Beschreibung** | Stellt eine Verbindung zu einer Excel-Datei her. Sie müssen dabei den Namen der Excel-Datei übergeben. Der Rückgabewert ist ein Handle auf die aktive Excel-Verbindung.
**Funktion** | odbc_ConnectToText
**Syntax** | function odbc_ConnectToText(FileName: String): Integer;
**Beschreibung** | Stellt eine Verbindung zu einer CSV-Text-Datei her. Sie müssen dabei den Namen der Text-Datei übergeben. Der Rückgabewert ist ein Handle auf die aktive Verbindung.
**Funktion** | odbc_ConnectToFirebird
**Syntax** | odbc_ConnectToFirebird(Server, Protocol, FileName, UserName, Password: String): Integer;
**Beschreibung** | Stellt eine Verbindung zu einer Firebird-Datenbank her. Sie müssen den Namen/IP-Adresse des Datenbankservers, das Protokoll (LOCAL, TCPIP), den Namen der Datenbankdatei, den Benutzernamen und das Kennwort übergeben. Der Rückgabewert ist ein Handle auf die aktive Datenbankverbindung.
**Funktion** | odbc_Disconnect
**Syntax** | procedure odbc_Disconnect(Connection: Integer);
**Beschreibung** | Löst eine Verbindung wieder auf und gibt die entsprechenden Ressourcen frei.
**Funktion** | odbc_StartTransaction
**Syntax** | procedure odbc_StartTransaction(Connection: Integer);
**Beschreibung** | Beendet den Auto-Commit-Modus und startet eine neue Transaktion.
**Funktion** | odbc_EndTransaction
**Syntax** | procedure odbc_EndTransaction(Connection: Integer);
**Beschreibung** | Beendet die aktuelle Transaktion durch ein Commit und schaltet um in den Auto-Commit-Modus.
**Funktion** | odbc_Commit
**Syntax** | procedure odbc_Commit(Connection: Integer);
**Beschreibung** | Führt ein Commit durch und startet anschließend eine neue Transaktion.
**Funktion** | odbc_Rollback
**Syntax** | procedure odbc_Rollback(Connection: Integer);
**Beschreibung** | Führt ein Rollback durch und startet anschließend eine neue Transaktion.
**Funktion** | odbc_CreateCatalog
**Syntax** | function odbc_CreateCatalog(Connection: Integer): Integer;
**Beschreibung** | Erzeugt einen Katalog, mit dessen Hilfe Meta-Daten zur Datenbank ausgelesen werden können.
**Funktion** | odbc_GetTableCount
**Syntax** | function odbc_GetTableCount(Catalog: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der definierten Tabellen einer Datenbank zurück.
**Funktion** | odbc_GetTableName
**Syntax** | function odbc_GetTableName(Catalog: Integer; Index: Integer): String;
**Beschreibung** | Liefert den Namen der mit Index indizierten Datenbanktabelle zurück.
**Funktion** | odbc_GetStoredProcCount
**Syntax** | function odbc_GetStoredProcCount(Catalog: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der definierten Prozeduren einer Datenbank zurück.
**Funktion** | odbc_GetStoredProcName
**Syntax** | function odbc_GetStoredProcName(Catalog: Integer; Index: Integer): String;
**Beschreibung** | Liefert den Namen der mit Index indizierten Datenbankprozedur zurück.
**Funktion** | odbc_DestroyCatalog
**Syntax** | procedure odbc_DestroyCatalog(Catalog: Integer);
**Beschreibung** | Gibt einen erstellten Katalog wieder frei.
**Funktion** | odbc_CreateCommand
**Syntax** | function odbc_CreateCommand(Connection: Integer; SQL: String): Integer;
**Beschreibung** | Erstellt einen SQL-Befehl, führt ihn aber noch nicht aus. Die Funktion liefert bei Erfolg ein Handle auf den erstellten Befehl zurück, andern falls 0.
**Funktion** | odbc_DestroyCommand
**Syntax** | procedure odbc_DestroyCommand(Command: Integer);
**Beschreibung** | Gibt einen mit odbc_CreateCommand erstellten SQL-Befehl wieder frei.
**Funktion** | odbc_Execute
**Syntax** | procedure odbc_Execute(Command: Integer);
**Beschreibung** | Führt einen mit odbc_CreateCommand erstellten SQL-Befehl aus. Dabei darf es sich nur um SQL-Befehle handeln, die als Ergebnis keine Datenmenge liefern (z.B. INSERT, UPDATE, DELETE).
**Funktion** | odbc_RowsAffected
**Syntax** | function odbc_RowsAffected(Command: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Datensätze zurück, die durch ein INSERT, UPDATE oder DELETE betroffen waren. Diese Funktion macht nur in Verbindung mit einem vorher ausgeführten odbc_Execute Sinn.
**Funktion** | odbc_Open
**Syntax** | procedure odbc_Open(Command: Integer);
**Beschreibung** | Öffnet eine mit odbc_CreateCommand erstellte SQL-Abfrage.
**Funktion** | odbc_EOF
**Syntax** | function odbc_EOF(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls der Datensatzeiger der mit Query verbundenen Abfrage am Ende der aktiven Datenmenge steht.
**Funktion** | odbc_BOF
**Syntax** | function odbc_BOF(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls der Datensatzeiger der mit Query verbundenen Abfrage am Anfang der aktiven Datenmenge steht.
**Funktion** | odbc_First
**Syntax** | procedure odbc_First(Query: Integer);
**Beschreibung** | Springt zum ersten Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | odbc_Next
**Syntax** | procedure odbc_Next(Query: Integer);
**Beschreibung** | Springt zum nächsten Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | odbc_Prior
**Syntax** | procedure odbc_Prior(Query: Integer);
**Beschreibung** |  Springt zum vorherigen Datensatz der mit Query verbundenen aktiven Datenmenge.  
**Funktion** | odbc_Last
**Syntax** | procedure odbc_Last(Query: Integer);
**Beschreibung** | Springt zum letzten Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | odbc_RecordCount
**Syntax** | function odbc_RecordCount(Query: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Datensätze innerhalb der mit Query verbundenen aktiven Datenmenge zurück.
**Funktion** | odbc_IsEmpty
**Syntax** | function odbc_IsEmpty(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls die mit Query verbundene aktive Datenmenge leer ist.
**Funktion** | odbc_IsActive
**Syntax** | function odbc_IsActive(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls die mit Query verbundene Datenmenge aktiv bzw. geöffnet ist.
**Funktion** | odbc_GetFieldCount
**Syntax** | function odbc_GetFieldCount(Query: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Felder der mit Query verbundenen aktiven Datenmenge zurück.
**Funktion** | odbc_GetFieldName
**Syntax** | function odbc_GetFieldName(Query: Integer; Index: Integer): String;
**Beschreibung** | Liefert den Feldnamen des mit Index indizierten Feldes der mit Query verbundenen aktiven Daten-menge zurück.
**Funktion** | odbc_GetFieldValue
**Syntax** | function odbc_GetFieldValue(Query: Integer; Name: String): Variant;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Variante zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab.
**Funktion** | odbc_GetFieldAsText
**Syntax** | function odbc_GetFieldAsText(Query: Integer; Name: String): String;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als String zurück. Der Feldwert hängt natür-lich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen String umgewandelt werden können, dann wird ein Leerstring zurückgeliefert.
**Funktion** | odbc_GetFieldAsInt
**Syntax** | function odbc_GetFieldAsInt(Query: Integer; Name: String; Default: Integer): Integer;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Integer zurück. Der Feldwert hängt natür-lich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Integer-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** | odbc_GetFieldAsFloat
**Syntax** | function odbc_GetFieldAsFloat(Query: Integer; Name: String; Default: Float): Float;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Float zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Float-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** | odbc_GetFieldAsBool
**Syntax** | function odbc_GetFieldAsBool(Query: Integer; Name: String; Default: Boolean): Boolean;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Boolean zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Boolean-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** | odbc_GetFieldAsDate
**Syntax** | function odbc_GetFieldAsDate(Query: Integer; Name: String): DateTime;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Datumsangabe zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in eine Datumsangabe umgewandelt werden können, dann wird 0 zurückgeliefert.
**Funktion** | odbc_GetFieldAsTime
**Syntax** | function odbc_GetFieldAsTime(Query: Integer; Name: String): DateTime;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Zeitangabe zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in eine Zeitangabe umgewandelt werden können, dann wird 0 zurückgeliefert.
**Funktion** | odbc_BindParam
**Syntax** | function odbc_BindParam(Command: Integer; Param: String; Value: Variant);
**Beschreibung** | Setzt den mit Param gekennzeichneten Parameter auf den Wert Value.
**Funktion** | odbc_BindParamToNull
**Syntax** | function odbc_BindParamToNull(Command: Integer; Param: String);
**Beschreibung** | Setzt den mit Param gekennzeichneten Parameter auf den Status NULL.
**Funktion** | odbc_GetErrorCount
**Syntax** | function odbc_GetErrorCount: Integer;
**Beschreibung** | Liefert die Anzahl der Fehler zurück, die seit dem letzten Löschen des Fehlerbuffers aufgelaufen sind.
**Funktion** | odbc_GetErrorMessage
**Syntax** | function odbc_GetErrorMessage(Index: Integer): String;
**Beschreibung** | Liefert den Text der mit Index indizierten Fehlermeldung zurück.
**Funktion** | odbc_GetErrorState
**Syntax** | function odbc_GetErrorState(Index: Integer): String;
**Beschreibung** | Liefert den Fehlerstatus der mit Index indizierten Fehlermeldung zurück.
**Funktion** | odbc_ClearErrors
**Syntax** | procedure odbc_ClearErrors;
**Beschreibung** | Löscht den internen Fehlerpuffer.
**Funktion** | odbc_GetErrorTotalCount
**Syntax** | function odbc_GetErrorTotalCount: Integer;
**Beschreibung** | Liefert die Anzahl aller jemals aufgetretenen Fehler zurück.

## IB-Bibliothek

Die IB-Bibliothek stellt Funktionen für den direkten Zugriff auf die aktuelle MAGELLAN-Datenbank zur Verfügung. Dies sind vor allem Funktionen zum Ausführen von SQL-Anweisungen (z.B. DELETE, UPDATE, INSERT oder SELECT).

Alle Funktionen besitzen den Präfix ib_.

Zu beachten ist, dass die SQL-Anweisungen im SQL3-Dialekt verlangt werden. Praktisch bedeutet dies, dass alle Feld- und Tabellennamen in Anführungszeichen und unter Beachtung der Groß- und Klein-schreibung angegeben werden müssen.

Titel|Inhalt
--|--
**Funktion** | ib_Commit
**Syntax** | procedure ib_Commit;
**Beschreibung** | Führt ein Commit durch und startet anschließend eine neue Transaktion.
**Funktion** | ib_Rollback
**Syntax** | procedure ib_Rollback;
**Beschreibung** | Führt ein Rollback durch und startet anschließend eine neue Transaktion.
**Funktion** | ib_CreateCommand
**Syntax** | function ib_CreateCommand(SQL: String): Integer;
**Beschreibung** | Erstellt einen SQL-Befehl, führt ihn aber noch nicht aus. Die Funktion liefert bei Erfolg ein Handle auf den erstellten Befehl zurück, andern- falls 0.
**Funktion** | ib_DestroyCommand
**Syntax** | procedure ib_DestroyCommand(Command: Integer);
**Beschreibung** | Gibt einen mit ib_CreateCommand erstellten SQL-Befehl wieder frei.
**Funktion** | ib_Execute
**Syntax** | procedure ib_Execute(Command: Integer);
**Beschreibung** | Führt einen mit ib_CreateCommand erstellten SQL-Befehl aus. Dabei darf es sich nur um SQL-Befehle handeln, die als Ergebnis keine Datenmenge liefern (z.B. INSERT, UPDATE, DELETE).
**Funktion** | ib_RowsAffected
**Syntax** | function ib_RowsAffected(Command: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Datensätze zurück, die durch ein INSERT, UP- DATE oder DELETE betroffen waren. Diese Funktion macht nur in Verbindung mit einem vorher ausgeführten ib_Execute Sinn.
**Funktion** | ib_Open
**Syntax** | procedure ib_Open(Command: Integer);
**Beschreibung** | Öffnet eine mit ib_CreateCommand erstellte SQL-Abfrage.
**Funktion** | ib_EOF
**Syntax** | function ib_EOF(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls der Datensatzeiger der mit Query verbundenen Abfrage am Ende der aktiven Datenmenge steht.
**Funktion** | ib_BOF
**Syntax** | function ib_BOF(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls der Datensatzeiger der mit Query verbundenen Abfrage am Anfang der aktiven Datenmenge steht.
**Funktion** | ib_First
**Syntax** | procedure ib_First(Query: Integer);
**Beschreibung** | Springt zum ersten Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | ib_Last
**Syntax** | procedure ib_Next(Query: Integer);
**Beschreibung** | Springt zum nächsten Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | ib_Prior
**Syntax** | procedure ib_Prior(Query: Integer);
**Beschreibung** | Springt zum vorherigen Datensatz der mit Query verbundenen aktiven Datenmenge.
**Funktion** | ib_RecordCount
**Syntax** | function ib_RecordCount(Query: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Datensätze innerhalb der mit Query verbundenen aktiven Datenmenge zurück.
**Funktion** | ib_IsEmpty
**Syntax** | function ib_IsEmpty(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls die mit Query verbundene aktive Datenmenge leer ist.
**Funktion** | ib_IsActive
**Syntax** | function ib_IsActive(Query: Integer): Boolean;
**Beschreibung** | Liefert TRUE zurück, falls die mit Query verbundenen Datenmenge aktiv bzw. geöffnet ist.
**Funktion** | ib_GetFieldCount
**Syntax** | function ib_GetFieldCount(Query: Integer): Integer;
**Beschreibung** |Liefert die Anzahl der Felder der mit Query verbundenen aktiven Datenmenge zurück.
**Funktion** |ib_GetFieldName
**Syntax** | function ib_GetFieldName(Query: Integer; Index: Integer): String;
**Beschreibung** | Liefert den Feldnamen des mit Index indizierten Feldes der mit Query verbundenen aktiven Datenmenge zurück.
**Funktion** | ib_GetFieldValue
**Syntax** | function ib_GetFieldValue(Query: Integer; Name: String): Variant;
**Beschreibung** |Liefert den Feldwert des mit Name bezeichneten Feldes als Variante zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab.
**Funktion** | ib_GetFieldAsText
**Syntax** |function ib_GetFieldAsText(Query: Integer; Name: String): String;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als String zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen String umgewandelt werden können, dann wird ein Leerstring zurückgeliefert.
**Funktion** | ib_GetFieldAsInt
**Syntax** | function ib_GetFieldAsInt(Query: Integer; Name: String; Default: Integer): Integer;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Integer zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Integer-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** | ib_GetFieldAsFloat
**Syntax** | function ib_GetFieldAsFloat(Query: Integer; Name: String; Default: Float): Float;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Float zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Float-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** | ib_GetFieldAsBool
**Syntax** | function ib_GetFieldAsBool(Query: Integer; Name: String; Default: Boolean): Boolean;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Boolean zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in einen Boolean-Wert umgewandelt werden können, dann wird Default zurückgeliefert.
**Funktion** |ib_GetFieldAsDate
**Syntax** | function ib_GetFieldAsDate(Query: Integer; Name: String): DateTime;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Datumsangabe zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in eine Datumsangabe umgewandelt werden können, dann wird 0 zurückgeliefert.
**Funktion** | ib_GetFieldAsTime
**Syntax** | function ib_GetFieldAsTime(Query: Integer; Name: String): DateTime;
**Beschreibung** | Liefert den Feldwert des mit Name bezeichneten Feldes als Zeitangabe zurück. Der Feldwert hängt natürlich von der Position des Datensatzzeigers innerhalb der aktiven Datenmenge ab. Sollte der Feldwert nicht in eine Zeitangabe umgewandelt werden können, dann wird 0 zurückgeliefert.
**Funktion** | ib_BindParam
**Syntax** |function ib_BindParam(Command: Integer; Param: String; Value: Variant);
**Beschreibung** | Setzt den mit Param gekennzeichneten Parameter auf den Wert Value.
**Funktion** | ib_BindParamToNull
**Syntax** | function ib_BindParamToNull(Command: Integer; Param: String);
**Beschreibung** | Setzt den mit Param gekennzeichneten Parameter auf den Status NULL.
**Funktion** | ib_GetErrorCount
**Syntax** | function ib_GetErrorCount: Integer;
**Beschreibung** | Liefert die Anzahl der Fehler zurück, die seit dem letzten Löschen des Fehlerbuffers aufgelaufen sind.
**Funktion** | ib_GetErrorMessage
**Syntax** | function ib_GetErrorMessage(Index: Integer): String;
**Beschreibung** | Liefert den Text der mit Index indizierten Fehlermeldung zurück.
**Funktion** | ib_GetErrorCode
**Syntax** | function ib_GetErrorCode(Index: Integer): String;
**Beschreibung** | Liefert den Fehlercode der mit Index indizierten Fehlermeldung zurück.
**Funktion** |ib_ClearErrors
**Syntax** | procedure ib_ClearErrors;
**Beschreibung** | Löscht den internen Fehlerpuffer.
**Funktion** | ib_GetErrorTotalCount
**Syntax** | function ib_GetErrorTotalCount: Integer;
**Beschreibung** | Liefert die Anzahl aller jemals aufgetretenen Fehler zurück.

## SDTF-Bibliothek

Die SDTF-Bibliothek stellt Funktionen für den Zugriff auf das textbasierte Schuldatentransferformat zur Verfügung.
Jede Textzeile stellt einen Datensatz dar, der wie folgt aufgebaut ist:

`<LineType>;<Field_1>;<Field_2>;...;<Field_n>`

Wichtig in diesem Zusammenhang ist, dass Felder, die ein Leerzeichen oder ein Semikolon enthalten, in Anführungszeichen (") geschrieben werden. Die Routinen dieser Bibliothek berücksichtigen dies automatisch, so dass ein Skript-Programmierer sich darum nicht kümmern braucht.

Titel|Inhalt
--|--
**Funktion** | sdtf_LoadFromFile
**Syntax** | sdtf_LoadFromFile(FileName: String): Integer;
**Beschreibung** | Lädt den gesamten Inhalt der Datei zur weiteren Bearbeitung in einen Buffer. Das Handle zum Buffer wird als Funktionsergebnis zurückgeliefert.
**Funktion** | sdtf_SaveToFile
**Syntax** | sdtf_SaveToFile(FileName: String; Buffer: Integer)
**Beschreibung** | Schreibt den Inhalt eines Buffers in eine Datei. Existiert die Datei bereits, so wird sie überschrieben.
**Funktion** | sdtf_CreateBuffer
**Syntax** | sdtf_CreateBuffer: Integer;
**Beschreibung** | Erzeugt einen neuen und leeren Buffer zur weiteren Bearbeitung. Das Handle zum Buffer wird als
**Funktion**sergebnis zurückgeliefert.
**Funktion** | sdtf_DestroyBuffer
**Syntax** | sdtf_DestroyBuffer(Buffer: Integer);
**Beschreibung** | Erzeugt einen neuen und leeren Buffer zur weiteren Bearbeitung. Das Handle zum Buffer wird als
**Funktion**sergebnis zurückgeliefert.
**Funktion** | sdtf_GetBufferLineCount
**Syntax** | sdtf_GetBufferLineCount(Buffer: Integer): Integer;
**Beschreibung** | Liefert die Anzahl der Textzeilen im Buffer zurück.
**Funktion** | sdtf_GetBufferLine
**Syntax** | sdtf_GetBufferLine(Buffer: Integer; Index: Integer): String;
**Beschreibung** | Liefert die Textzeile an der Position Index im Buffer zurück.
**Funktion** | sdtf_AddBufferLine
**Syntax** | sdtf_AddBufferLine(Buffer: Integer; Line: String);
**Beschreibung** | Fügt eine neue Textzeile an den Buffer an.
**Funktion** | sdtf_DeleteBufferLine
**Syntax** | sdtf_DeleteBufferLine(Buffer: Integer; Index: Integer);
**Beschreibung** | Löscht eine Textzeile an der Posiiton Index im Buffer.
**Funktion** | sdtf_GetFieldCount
**Syntax** |sdtf_GetFieldCount(Line: String): Integer;
**Beschreibung** | Liefert die Anzahl der Felder (bzw. Werte) in der übergebenen Textzeile zurück.
**Funktion** | sdtf_GetFieldValue
**Syntax** | sdtf_GetFieldValue(Line: String; Index: Integer): String;
**Beschreibung** |Liefert den Wert an der Position Index in der übergebenen Textzeile zurück.
**Funktion** | sdtf_GetFieldValueAsText
**Syntax** | sdtf_GetFieldValueAsText(Line: String; Index: Integer): Variant;
**Beschreibung** | Liefert den Wert an der Position Index in der übergebenen Textzeile zurück.
**Funktion** | sdtf_GetFieldValueAsInteger
**Syntax** | sdtf_GetFieldValueAsInteger(Line: String; Index: Integer): Variant;
**Beschreibung** | Liefert den Wert an der Position Index in der übergebenen Textzeile zurück.
**Funktion** | sdtf_AddFieldValue
**Syntax** | sdtf_AddFieldValue(Line: String; Value: Variant): String;
**Beschreibung** | Fügt einen neuen Wert an das Ende der übergebenen Textzeile an.
**Funktion** | sdtf_IsErro
**Syntax** | sdtf_IsError: Boolean;
**Beschreibung** | Gibt TRUE zurück, falls ein oder mehrere Fehler beim Dateizugriff aufgetreten sind.
**Funktion** | sdtf_GetErrorCount
**Syntax** | sdtf_GetErrorCount: Integer;
**Beschreibung** |Liefert die Anzahl der Fehler zurück, falls ein oder mehrere Fehler beim Dateizugriff aufgetreten sind.
**Funktion** | sdtf_GetErrorMessage
**Syntax** | sdtf_GetErrorMessage(Index: Integer): String;
**Beschreibung** | Liefert die Fehlermeldungen zurück, falls ein oder mehrere Fehler beim Dateizugriff aufgetreten sind.
**Funktion** | sdtf_ClearErrors
**Syntax** |sdtf_ClearErrors;
**Beschreibung** | Löscht alle angelaufenen Fehlermeldungen.

## BOX-Bibliothek

Diese Skript-Bibliothek stellt ein Ausgabefenster zur Verfügung, mit dessen Hilfe der aktuelle Status der Skriptbearbeitung visualisiert werden kann. Zudem bekommt der Benutzer die Möglichkeit, das Skript vorzeitig abzubrechen.

Titel|Inhalt
--|--
**Funktion** | obox_Create
**Syntax** | procedure obox_Create(Caption: String; Size: Integer);
**Beschreibung** | Initialisiert das Ausgabefenster, zeigt es aber noch nicht an. Mit „Caption“ kann die Überschrift des Fensters festgelegt werden. Mit „Size“ die Größe des Laufbalkens. Bei Size = 0 wird kein Laufbalken angezeigt.
**Funktion** | obox_Destroy
**Syntax** | procedure obox_Destroy;
**Beschreibung** | Gibt die mit dem Ausgabefenster verbundenen Ressourcen wieder frei.
**Funktion** | obox_Show
**Syntax** |procedure obox_Show;
**Beschreibung** | Zeigt das Ausgabefenster an.
**Funktion** |obox_Hide
**Syntax** | procedure obox_Hide;
**Beschreibung** | Versteckt das Ausgabefenster.
**Funktion** | obox_Ready
**Syntax** | procedure obox_Ready;
**Beschreibung** | Zeigt an, dass der Vorgang beendet ist. Der Benutzer kann nur noch mit OK bestätigen.
**Funktion** | obox_KeepAlive
**Syntax** |procedure obox_KeepAlive;
**Beschreibung** | Normalerweise muss diese Routine nicht aufgerufen werden. Sollte jedoch für längere Zeit keine neue Ausgabe im Fenster erscheinen, so kann das Multitasking-Verhalten darunter leiden. In diesen Fällen sollte man diese Routine häufiger aufrufen.
**Funktion** | obox_StepIt
**Syntax** |procedure obox_StepIt;
**Beschreibung** | Setzt den Fortschrittsbalken eins weiter.
**Funktion** |obox_AddMsg
**Syntax** | procedure obox_AddMsg(Value: String);
**Beschreibung** | Gibt eine neue Meldung in Form einer neuen Zeile aus.
**Funktion** | obox_ExpandMsg
**Syntax** | procedure obox_ExpandMsg(Value: String);
**Beschreibung** | Fügt neuen Text an die aktuelle Meldung dran. Die aktuelle Meldung kann also erweitert werden.
**Funktion** | obox_ReplaceMsg **Syntax** | procedure obox_ReplaceMsg(Value: String);
**Beschreibung** | Ersetzt die aktuelle Meldung komplett durch eine neue Meldung.
**Funktion** | obox_IsAborted
**Syntax** | function obox_IsAborted: Boolean;
**Beschreibung** | Liefert TRUE zurück, falls der Benutzer auf "Abbrechen" gedrückt hat.
**Funktion** | obox_MsgCount
**Syntax** |function obox_MsgCount: Integer;
**Beschreibung** | Liefert die Anzahl der Meldungen zurück, die im Ausgabefenster angezeigt werden.

## Weitere Dienstfunktionen

Neben den eben beschriebenen Bibliotheken gibt es noch eine Reihe von Dienstfunktionen, die einem das Leben sehr erleichtern können.

Titel|Inhalt
--|--
**Syntax** |function VarIsNull(Value: Variant): Boolean;
**Beschreibung** | Diese Funktion liefert TRUE zurück, falls Value den Status NULL besitzt, ansonsten FALSE.
**Funktion** | MatchStr
**Syntax** | function MatchStr(InputStr, Wilds: String; IgnoreCase: Boolean): Boolean;
**Beschreibung** | MatchStr vergleicht InputStr mit Wilds. Der Parameter Wilds kann dabei die Wildcards "?" und "*" enthalten. Past Wilds zu InputStr, so liefert die Funktion TRUE zurück.
**Funktion** | ConcatStr
**Syntax** |function ConcatStr(S1, S2, Link: String): String;
**Beschreibung** | Verbindet die beiden Strings S1 und S2 miteinander. Ist weder S1 nochS2 leer, dann wird der Ver-bindungsstring Link dazwischengesetzt.
