# Datentypen und Operatoren

Ein Computer ist grundsätzlich dumm. Damit ein Computer weiß, wie er Werte einordnen soll, muss man ihm das explizit mitteilen. Eine solche Einordnung ist wichtig, damit ein Computer beispielsweise Zahlen von Wörtern unterscheiden kann.
Eine Kategorie in diesem Kontext bezeichnet man als **Datentyp**. Datentypen können also Zahlen, Zeichenketten, Wahrheitswerte (wahr oder falsch) und vieles mehr sein.

Mithilfe der Kategorisierung durch Datentypen, weiß ein Computer, was er mit dem jeweiligen Wert anfangen kann und was nicht.
Am besten lässt sich das mithilfe von **Operatoren** zeigen. Operatoren sind Rechenzeichen oder andere Akteure, die zwei (oder mehr) Werte miteinander verknüpfen und damit einen neuen Wert erzeugen.

>Python macht es uns leicht, indem Python sich aus dem angegebenden Wert erschließt um welchen Datentyp es sich handelt und kümmert sich selbst darum dem Computer das genauer mitzuteilen - das machen viele andere Programmiersprachen nicht!
>Das bringt uns Entwicklern viel Freiheit, aber gleichzeitig müssen wir umso mehr aufpassen richtig und strukturiert mit unseren Daten umzugehen.

## Beispiele

**Zeichenkette - `str`**
String ist der Datentyp für einfachen Text. Den benutzen wir beispielsweise mit der `print` - Funktion, die wir schon eher kennengelernt haben.

Man kann sie miteinander addieren, dann fügt man sie aneinander:

```shell
>>> "Hello " + "World"
Hello World
```

> Hinweis: man kann sie **nur** miteinander addieren. Addition zwischen Strings und anderen Datentypen ist nicht möglich!

Man kann sie auch mit einer Ganzzahl multiplizieren:

```shell
>>> "ha" * 5
hahahahaha
```

**Ganzzahlen - `int`**
Der `int` - Datentyp ist ein primitiver Datentyp, also ein sehr grundlegender Datentyp.
Mit ihm kann man alles machen, was man mit Ganzen Zahlen so machen kann, von addieren bis hin zu potenzieren (sagt man das?)

```shell
>>> 5 + 5 
10
>>> 5 * 5
25
>>> 5 ** 2
25
```


**Wahrheitswerte - `bool`**
Boolsche Werte können genau zwei Werte annehmen `True` oder `False`. 
Die werden interessant, sobald Bedingungen ins Spiel kommen.


## Komplexe Datentypen

Die obigen Beispiele waren nur für primitive Datentypen und davon auch nicht alle. Eine vollständigere Auflistung findet ihr weiter unten (oder einfach im Internet, das ist auch eine sehr gute Quelle). Spannend wird es, wenn wir Listen und andere Datentypen ins Spiel bringen.
Sehr oft wollen wir eine Gruppe ähnlicher Informationen speichern und für jeden Wert eine eigene Variable zu deklarieren ist irgendwann einfach nicht mehr lustig bzw. wissen wir manchmal gar nicht, wie viele Werte wir genau erwarten.

### Listen

Listen in Python muss man sich wie Hermines Handtasche vorstellen: man kann jederzeit so viel rein tun, wie man möchte, aber gleichzeitig wird Ordnung gewahrt. Jedes Element einer Liste hat nämlich einen zugehörigen Index, der die Position des Elemets beschreibt. Dieses besagte Element kann alles sein: ein String, eine Zahl, ein Boolean, _noch eine Liste_ - man kann sie befüllen, wie ein Wahnsinniger.

```python
obst = ["apfel", "birne", "tomate", "mega-frucht"]  # das ist eine Liste
kram = ["wort", 3, 3.56, True, False, ["noch eine Liste?", "oh ja"]]  # das auch
brieftasche = []  # auch das ist eine Liste. Sie ist leer
```

Es gibt auch Operatoren, die mit Listen funktionieren.
Man kann zwei Listen miteinander addieren:

```shell
>>> ["w", 3] + [ 2, 2, 2 ]
["w", 3, 2, 2, 2]
```

> Auch hier gilt wieder: Man kann Listen nur mit anderen Listen addieren!

Auch Listen kann man mit Ganzzahlen multiplizieren, genauso wie auch bei Strings.

```shell
>>> [3, 4, 5] * 3
[3, 4, 5, 3, 4, 5, 3, 4, 5]
```

Was geht und was nicht findet man immer am besten heraus, wenn man es einfach ausprobiert ;).

Listen selbst stellen auch Funktionalitäten bereit, um sie in vollem Umfang zu benutzen.
Um an Listen ein Element anzuhängen brauchen wir die `append` Methode.
Die wird allerdings etwas anders benutzt als die bisher bekannte `print` oder `input` Funktion.

```python
meine_liste = [1, 2, 3]
meine_liste.append(4)
```

Der Hauptunterschied zwischen z.B. `print` und `append` in diesem Fall, ist dass `append` an die Liste mit einem `.` angehangen wird.
Die `append` - Methode wird über die Liste selbst aufgerufen und modifiziert diese. Die Funktion hat keinen Rückgabewert, weil der hier nicht benötigt wird.
Der Grund für die Unterscheidung wird klar, sobald man sich etwas mehr Programmierwissen angeeignet hat, aber so grundsätzlich kann man sich erstmal folgendes merken: Wenn eine von Python bereitgestellte Funktion auf einem Objekt selbst agiert, dann wird es mit einem Punkt angehangen. Ansonsten ruft man sie einfach so auf und gibt das betreffende Objekt als Parameter mit (Parameter werden später bei Funktionen noch näher erklärt).

Um ein bestimmtes Element der Liste aufzurufen, schreiben wir in eckigen Klammern hinter die Liste den Index unseres Elements.

```python
meine_liste = ["apfel", "birne", 12]
zweites_element = meine_liste[1]

print(zweites_element)  # gibt uns "birne" aus
```

> Wie bestimmt aufgefallen ist, wird das zweite Element hier mit dem Index 1 erreicht. Das liegt daran, dass in Python Indizes grundsätzlich mit 0 beginnen, sodass man immer Position - 1 im Kopf rechnen muss, wenn man ein Element einer Liste haben möchte.

Wir können jetzt also Listen erstellen, befüllen und einzelne Elemente auslesen. Um Elemente aus der Liste zu entfernen gibt es unterschiedliche Herangehensweisen.

```python
meine_liste = ["a", "b", "c"]

meine_liste.remove("a")  # Entfernt das Element "a" aus der Liste
meine_liste.pop(0)  # Gibt das Element am angegebenen Index zurück und löscht es
                    # dann aus der Liste
del meine_liste[0]  # Entfernt das Element am angegebenen Index 
```

### Dictionaries

Wenn uns eine Liste nicht reicht und wir eine etwas komplexere Struktur brauchen, kommen uns **Dictionaries** zur Hilfe. Dictionaries speichern Daten nach dem Key - Value Prinzip. Der Key (oder Schlüssel) identifiziert den Value (oder Wert) dabei eindeutig. Das bedeutet, dass jeder Schlüssel genau einmal existieren kann und es da keine Dopplungen geben kann. Der Wert hat keine solche Beschränkung.

```python
mein_dict = { "key1": "value", "key2": "value" }
```

Ein Beispiel in der Anwendung hierfür wäre Dictionaries als Adressbuch zu verwenden:

```python
kontaktdaten = { 
	"Cariem El Wakil" : {
		"tel_num": "0123456789",
		"straße": "Hauptstraße",
		"hausnummer": 34,
	},
	"Friederike Hochmuth" : {
		"tel_num": "0987654321",
		"straße": "Hauptstraße",
		"hausnummer": 34,
	}
}	
```

In diesem Beispiel habe ich Namen als Schlüssel verwendet und als Wert ein weiteres Dictionary, in dem wiederum neue Infos mit drin stehen

## Referenz

### Primitive Datentypen
| Python Typ | Englische Bezeichnung | Erklärung | Code Beispiel |
|----|----|----| ----|
| `str` | String | Zeichenkette | `'This is a python string'` |
| `int` | Integer | Ganzzahl | `1337` |
| `float` | Float | Dezimalzahl | `13.37` |
| `bool` | Boolean | Wahrheitswert | `True` oder `False` |
| `NoneType` | None Type | Leerer Wert (nicht 0!) | `none` |


### Komplexere Datentypen
| Python Typ | Englische Bezeichnung | Erklärung | Code Beispiel |
|----|----|----| ----|
| `complex` | Complex Number | Komplexe Zahl | `3j` |
| `list` | List | Liste von Werten | `[1, 'apfel', 23.8, True, [2,3,4]]` |
| `tuple` | Tuple | Geordnete, unveränderbare Liste von Werten | `(1, 2, '2')` |
| `dict` | Dictionary | Key - Value Paare | `{ 'key': 'value', 1: 2.5 }` |

### Operatoren
| Zeichen | Funktion                       | Beispiel                                                                                |
| ------- | ------------------------------ | --------------------------------------------------------------------------------------- |
| `+`     | Addition                       | `1 + 2` => `3`, `'apfel' + 'birne'` => `'apfelbirne'`                                   |
| `-`     | Subtraktion                    | `2 - 1` => `1`                                                                          |
| *       | Multiplikation                 | `2 * 2` => `4`, `"hi" * 3` => `"hihihi"`                                                |
| /       | Division                       | `6 / 3` => `2.0` (Die Division von Ganzzahlen hat immer eine Dezimalzahl als Ergebnis!) |
| //      | Ganzzahl Division (abgerundet) | `7 // 3` => `2`                                                                         |
| %        |   Restdivision                             |       `7 % 3` => `1`                                                                      |
| **      | Potenz                         | `2 ** 3` =>   `8`                                                                       |

### Nützliche Funktionen
| Name | Funktion | Beispiel |
|----|-----|-----|
| `type()` | Gibt den Typ eines Wertes wieder | `type(5)` => `<class 'int'>` |
|`str()`| Wandelt einen Wert in seine String Repräsentation um (existiert auch für die anderen Datentypen) | `string(5)` => `'5'` |
