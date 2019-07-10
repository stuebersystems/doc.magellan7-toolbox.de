# Skriptsprache

Die benutzte Skriptsprache „DelphiWebScript“ ist eine Variante der bekannten Programmiersprache „Object Pascal“. Wer also schon einmal mit der Entwicklungsumgebung Delphi gearbeitet hat, der wird sich gleich zu Hause füllen. Aber auch für Basic-Programmierer wird der Umstieg nicht schwer fallen. Eine detaillierte Beschreibung aller Sprachkonstrukte würde den Rahmen dieser Dokumentation sprengen. Sollten Sie mit Pascal bzw. mit Delphi nicht vertraut sein, so sollten Sie sich ein entsprechen-des Buch aus dem Fachhandel besorgen. Aber auch im Internet werden Sie zu diesem Thema fündig. Die beste Referenz stellen jedoch immer noch die mitgelieferten Skripte dar. Im Folgenden geben wir die vollständige Beschreibung der Syntax wieder und gehen auf Besonderheiten der Skriptsprache ein.

## Die Syntax

Die Syntax von DelphiWebScipt wird im folgenden Abschnitt in EBNF (Erweiterter Backus-Naur-Form) beschrieben. Wer mit dieser Beschreibungssprache nicht vertraut ist, kann unter diesem Stichwort weitere Erläuterungen z.B. in Fachbüchern oder über eine Internet-Recherche finden.

Es gelten folgende Beschreibungskonventionen:

Wert|Bedeutung
--|--
„[ ]“|Angaben in eckigen Klammern („[ ]“) sind optional.
„{ }“|Angaben in geschweiften Klammern („{ }“) können sich gar nicht, einmal oder mehrmals wiederholen.
Bezeichner in Großbuchstaben|Bezeichner in Großbuchstaben sind Symbole, d.h. Nicht-Terminal- Symbole.
Bezeichner in Anführungszeichen|Bezeichner in Anführungszeichen („Bezeichner“) sind Teil des Eingabetexts, d.h. Terminal-Symbole.
SCRIPT|Das Startsymbol ist SCRIPT.

```dws
SCRIPT =

[ ROOTSTATEMENT { ";" ROOTSTATEMENT } [ ";" ] ]


ROOTSTATEMENT =
TYPEDECL | PROCDECL | STATEMENT


STATEMENT =
VARDECL | CONSTDECL | BLOCK


VARDECL =
"var" NAME ":" TYPEDEF [ "=" EXPR ]


TYPEDECL =
"type" NAME "=" TYPEDEF


TYPEDEF =
„Boolean" | "Integer" | "Float" | "String" | „DateTime" | "Variant" | NAME | ARRAY-DEF | RECORDDEF | CLASSDEF

ARRAYDEF =
"array" "[" EXPR ".." EXPR {"," EXPR ".." EXPR} "]" "of" TYPEDEF


RECORDDEF =
"record" ARGLIST "end"


ARGLIST =
ARGDECL { ";" ARGDECL }


ARGDECL =
NAME ":" TYPEDEF


CLASSDEF =
"class" [ "(" NAME ")" ]
[ "private" | "public" | "protected" ] [ ARGLIST ";" ]
[ METHODDECL { ";" METHODDECL } ";" ]
[ "property" NAME ":" TYPEDEF [ "read" NAME ] [ "write" NAME ] ";" ]
"end"

METHODDECL =
[ "class" ] "procedure" NAME ["(" [ARGLIST] ")"]
[ ";" "override" | "virtual" | "reintroduce" ] |
[ "class" ] "function" NAME ["(" [ARGLIST] ")"]
":" TYPEDEF [ ";" "override" | "virtual" | "reintroduce" ] |
"constructor" NAME ["(" [ARGLIST] ")"] [ ";" "override" |
"virtual" | "reintroduce" ] |
"destructor" NAME ["(" [ARGLIST] ")"] [ ";" "override" | virtual" |
     "reintroduce" ]

PROCDECL =
PROCHEAD ";" PROCBODY |
PROCHEAD ";" "forward" |
METHODDEF ";" PROCBODY


PROCHEAD
"procedure" NAME ["(" [ARGLIST] ")"]
"function" NAME ["(" [ARGLIST] ")"] ":" TYPEDEF


PROCBODY =
{VARDECL ";"} "begin" SCRIPT "end"


METHODDEF =
[ "class" ] "procedure" NAME "." NAME ["(" [ARGLIST] ")"] |
[ "class" ] "function" NAME "." NAME ["(" [ARGLIST] ")"] ":" TYPEDEF |
"constructor" NAME "." NAME ["(" [ARGLIST] ")"] |
"destructor" NAME "." NAME ["(" [ARGLIST] ")"]


CONSTDECL =
"const" "=" EXPR


BLOCK =
"begin" [STATEMENT {";" STATEMENT} [";"]] "end" | INSTR


INSTR =
"if" EXPR "then" BLOCK |
"if" EXPR "then" BLOCK "else" BLOCK | CASEINSTR |
"for" VAR ":=" EXPR "to" EXPR "do" BLOCK |
"for" VAR ":=" EXPR "downto" EXPR "do" BLOCK |
"while" EXPR "do" BLOCK |
"repeat" [BLOCK {";" BLOCK} [";"]] "until" EXPR |
VAR ":=" EXPR |
FUNC |
EXCEPT |
FINALLY |
BLOCK

CASECOND =
EXPR | EXPR ".." EXPR |


CASEINSTR =
"case" EXPR "of"
{ CASECOND {"," CASECOND } : BLOCK ";" }
[ "default" ":" BLOCK ";" ]
"end"


FUNC =
NAME [ "(" [EXPR {, EXPR}] ")" ]


EXCEPT =
"try"
BLOCK { ";" BLOCK } [ ";" ]
"except"
{ "on" NAME ":" NAME "do" BLOCK; }
"end"


FINALLY =
"try"
BLOCK { ";" BLOCK } [ ";" ]
"finally"
{ "on" NAME ":" NAME "do" BLOCK; }
"end"


EXPR =
EXPRADD [ "=" | "+" | "-" | "OR" EXPRADD]


EXPRADD =
EXPRMUL [ "+" | "-" | "OR" EXPRADD]


EXPRMUL =
TERM [ "*" | "/" | "mod" | "div" EXPRMUL]


TERM =
"+" TERM |
"-" TERM |
"not" TERM |
CONST | VAR | FUNC | "(" EXPR ")"


CONST =
INT |HEXINT |FLOAT |
STR |CHAR |
"True" | "False"


VAR =
NAME |
NAME "[" INT "]" |
NAME "." VAR |
VAR "." FUNC


NAME =
LIT {LIT | "0".."9" | "_"}

LIT =
"A".."Z", "a".."z"


STR =
	CHAR | STRING { CHAR [ STRING ] }
 
 
STRING =
" ' " { STRINGCHAR } " ' " { " ' " STRING }


STRINGCHAR =
ASCII(0)..ASCII(255) - " ' " - ASCII(13) | " ' ' "


CHAR =
"#" INT | "#" HEXINT


HEXINT =
"$" HEXNUM { HEXNUM }


HEXNUM =
"0".."9" | "A".."F" | "a".."f"


FLOAT =
INT [ "." INT] [ "E" | "e" ["+" | "-"] INT ]
 
 
INT =
NUM {NUM}


NUM =
"0".."9"
```

## Reservierte Worte

Die folgenden Worte sind reserviert und können nicht beliebig im Skript verwendet werden. So dürfen Sie beispielsweise keine Variable deklarieren, die BEGIN heißt.

Buchstabe|Reservierter Begriff
--|--
A| and   array   as
B|begin  
C|case   class   const   const   constructor
D|destructor   div    do     downto
E|else   end   except
F|finally     for    forward    function
I|if     inherited    is
L|label
M|mod
N| nil    not  
O|of     or  
P|procedure     property  
R| raise    record   repeat
S|string
T| then   to    try     type
U| until  
V| var  
W|while  
X|xor  

## Besonderheiten

Da DelphiWebScript an die Programmiersprache der Entwicklungsumgebung Delphi angelehnt ist, ist es das Beste, die Unterschiede zu Delphi zu erläutern.

### Struktur

Die Syntax von DelphiWebScript unterscheidet sich in einigen Punkten von einem Delphi-Programm. Ein wesentlicher Unterschied ist die Tatsache, dass in DelphiWebScript nicht zwischen Deklarationsteil und Programmteil unterschieden wird.

Ein Delphi-Programm hat die folgende Struktur:

```dws

program ProgramName;

Declarations

begin

Instructions

end.
```

Ein DelphiWebScript hat keine Struktur. Man kann Deklarationen und Instruktionen überall im Skript platzieren. Daher beginnt jede Deklaration mit einem Schlüsselwort und endet mit einem Semikolon.

Beispiel:

```dws
var i: Integer = 2;
type TPoint = record x, y: Integer; end;
type TRect = record x, y, w, h: Integer end;

var r: TRect;
r.x := 3;

procedure Proc(x: Integer); begin end;

Proc(x);
```

### Deklarationen

Sie können innerhalb einer Prozedur-Deklaration keine Deklaration platzieren.

**Beispiel:**

```dws
// FALSCH
procedure Proc(x: Integer);
type
TMyRec = record a, b: string end;
begin end;
```

```dws
// RICHTIG
procedure Proc(x: Integer);
begin
type TMyRec = record a, b: string end;
end;
```

Dafür kann man Variablen auch innerhalb eines Blocks (BEGIN..END) deklarieren. Die Deklaration ist nur innerhalb dieses Blocks und inner- halb der entsprechenden Unterblöcke sichtbar.

**Beispiel:**

```dws
var i: Integer;
if i = 0 then begin
var j: Integer;
j := 2;
while j > 0 do
begin
var k: Integer;
k := 2;
j := j - k;
end;
end;

var j: String;
// Variable "j"´, die innerhalb des
// if-Blocks deklariert wurde, ist hier nicht sichtbar!
```

### Datentypen

DelphiWebScript unterstützt nur folgende elementare Datentypen:

Typ|Beschreibung
---|-----------
Integer| 32Bit-Integer
Float|64Bit-Fließkommawert
String| Textfeld beliebiger Länge
Boolean|Kann die Werte TRUE oder FALSE annehmen.
DateTime|Datum-Zeit-Angabe, ist kompatibel zu Float.
Variant|Umfasst alle anderen Typen. Sie können einer Variable des Typs Variant jeden anderen elementaren Typ zuweisen.

### Mengentypen

DelphiWebScript unterstützt keine Mengentypen und keine Aufzählungstypen.

#### Case-Anweisung

In DelphiWebSkript können Sie innerhalb einer CASE-Anweisung alle Datentypen verwenden:

**Beispiel:**

```dws
var s: string;

s := 'Alpha';

case s of
'Alpha': DoSomething;
'Beta', 'Gamma': DoSomethingElse;
end;
```

##### Initialisierung{#Initialisierung}

Sie können eine Variable mit einer modifizierten VAR-Anweisung initialisieren:

**Beispiel:**

```dws
var s: Integer = 2;
var str: String = 'Hello' + IntToStr(s);
var i: Integer = 12;
 ```

Eine Initialisierung entspricht einer Deklaration gefolgt von einer Zuweisung. Sie ist lediglich eine Abkürzung dafür. Der Unterschied besteht allerdings in der Ausführung der Anweisung: Die Initialisierung wird nur genau einmal vom Compiler durchlaufen. Die Anweisung wird zur Ausführungszeit des Programms ggf. mehrmals durchlaufen.

**Beispiel:**

```dws
var i: Integer = 12;
//…entspricht…
var i: Integer; i := 12;
```
