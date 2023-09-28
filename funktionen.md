# Funktionen

Funktionen sind eins der wichtigsten und flexibelsten Konzepte in der Programmierung.
Durch sie kann man Dopplungen vermeiden, Komplexität verringern und die Lesbarkeit des Programms deutlich steigern.

Wir kennen Funktionen bereits von den Python-built-in Funktionen, wie `print` oder `input`.

## Anwendung

Sobald sich mehrere Zeilen in einem Programm doppeln, oder ein Abschnitt zu lang und verworren wird, sollte man Funktionen schreiben um den Code besser zu strukturieren und letztendlich lesbar zu machen.

## Aufbau

```python
def function_name(parameter_one, parameter_two):
	print('Code Block')
```

Eine Funktionsdeklaration besteht aus der Funktionssignatur und einem Codeblock.
Die **Funktionssignatur** identifiziert die Funktion, das bedeutet es kann keine zwei Funktionen haben, die die gleiche Signatur haben. Der **Code Block** verhält sich hier genau, wie auch bei [Verzweigungen und Schleifen](verzweigung_und_schleifen.md).

Eine Funktionsdeklaration leitet man mit dem Schlüsselwort `def` gefolgt vom Namen, den man der Funktion geben möchte: `def my_function...` . 
Anschließend gibt man in Klammern die Parameter der Funktion an.
**Parameter** benutzen wir, wenn wir der Funktionen Informationen übergeben müssen.

Wenn wir also beispielsweise eine Funktion schreiben wollen, die den Nutzer beim Namen begrüßt, muss unsere Funktion irgendwoher wissen, wen sie begrüßen soll.

```python
def greet(name):
	print(f"Hello {name}")
```

Die Anzahl an Parametern ist dabei nicht beschränkt (keine Parameter zu haben ist auch möglich).

Um die Funktion dann aufzurufen, machen wir das genau so, wie auch bei `print` und `input` :

```python
greet("Steve")
```

Das gibt uns dann die Ausgabe:

```bash
$ Hello Steve
```

---

Funktionen können zusätzlich zu Eingabeparametern auch Rückgabewerte haben.
Zum Beispiel: die `input` - Funktion gibt die Eingabe des Nutzers zurück.
Wenn eine Funktion einen Rückgabewert besitzt können wir sie auf der rechten Seite einer Zuweisung aufrufen und damit ihren Wert an eine Variable geben.
Damit eine Funktion einen Rückgabewert bekommt brauchen wir das `return` - Schlüsselwort.
Nachdem das `return` - Statement ausgeführt wurde, wird keine darauffolgende Zeile in der Funktion ausgeführt.

```python
def add_five(number):
	return number + 5

sum = add_five(4)
print(sum)
```

Führen wir diesen Code aus wird uns die Zahl `9` ausgegeben.

---

Manchmal ist es nicht völlig eindeutig, welchen [Datentyp](datentypen.md) der Rückgabewert oder die Parameter einer Funktion haben.
Das ist wichtig zu wissen, da man mit unterschiedlichen Datentypen unterschiedliche Dinge tun kann - und nicht kann!
Damit man sich nicht alles merken muss und den Texteditor in voller Fülle nutzt kann man Hinweise in der Funktionssignatur hinterlassen.

```python
def add_five(number: int) -> int:
	return number + 5
```
