# Verzweigungen und Schleifen

## Verzweigungen

Damit Programme Entscheidungen für uns treffen können, müssen wir ihnen mitteilen, wie sie diese vorzunehmen haben.
Das passiert mithilfe von `if`- Anweisungen.

In diesen wird eine Bedingung auf ihren Wahrheitswert (oder Boolean) überprüft und abhängig vom Ergebnis wird der
dementsprechende Code ausgeführt.

Die Bedingung ist ein Ausdruck, den man zu entweder `True` oder `False` auswerten kann.
Man kann Ausdrücke mit anderen Ausdrücken über logische Operatoren (`and`, `or`) verknüpfen.

**Beispiele:**

Vergleiche auf Gleichheit

```bash
>>> 1 == 1
True
>>> 1 == 2
False
>>> 'apfel' == 'birnen'
False
>>> type('apfel') == type('birnen')
True
```

Vergleiche auf Ungleichheit

```bash
>>> 1 != 1
False
>>> 1 != 2
True
>>> 'apfel' != 'birnen'
False
```

Wenn wir unsere Bedingungen formuliert haben, können wir sie unserer `if` - Anweisung übergeben und festlegen, was denn tatsächlich passieren soll.

```python
if 1 == 2:
	print("Das geht doch gar nicht!")
```

In Python schreiben wir die Bedingung hinter das Schlüsselwort `if` und dahinter einen Doppelpunkt.
Die darauffolgenden Zeilen beschreiben dann, was im Fall die Bedingung trifft zu, passieren soll.

> **WICHTIG: Ab der Zeile nach der Bedingung ist alles um eine Einheit eingerückt, was auf der selben Hierarchiestufe passiert.**
> Python legt sehr großen Wert auf die Einrückung, sobald etwas nicht richtig eingerückt ist, ist das Programm sofort fehlerhaft.

Eine Verzweigung würde nicht "Verzweigung" heißen, wenn es nicht mehrere Zweige geben würde.
Für eine einfache Verzweigung gibt es das `else`, dessen Code ausgeführt wird, wenn die Bedingung zu `False` ausgewertet wird.

```python
if 1 == 2:
    print("Das geht doch gar nicht!")
else:
    print("Das hier wird dann tatsächlich ausgegeben")
```

Falls man an einer Stelle mehr als zwei Ereignisse erwartet, gibt es die Möglichkeit mit einem `elif` ("else if") diese weiteren Ereignisse abzufangen und sicher zu stellen, dass nur eins davon zutrifft.

```python
if name == "Steve":
    print("Sachen, die ich Steve erzählen will")
elif name == "Steve A.":
    print("Sachen, die ich Steve A. erzählen will")
else:
    print("Das erzähle ich jedem anderen.")
```

***

## "For" - Schleifen

Wenn wir eine Aufgabe haben, die wir eine bestimmte Anzahl an Malen ausführen wollen, oder für jedes Element einer Liste die gleiche Sache tun wollen, dann kommen `for` - Schleifen ins Spiel.
`for` - Schleifen => "Für alle ___ in ___ "
In Python läuft das wie folgt:

1. Wir leiten mit dem `for` - Schlüsselwort ein
2. Dann legen wir einen Platzhalternamen fest mit dem wir auf das jeweilige Element referenzieren => `for element`
3. Danach bestimmen wir woher die Elemente kommen, wie zum Beispiel einer Liste, gefolgt von einem Doppelpunkt => `for element in element_list:`
4. Jetzt fehlt nur noch der Code den wir für jedes Element in der List ausführen wollen

```python
names = ["GladOS", "WALL-E", "Eevee"]
for name in names:
	print(f"Hello {name}!")
```

> **Hinweis:** Auch hier muss alles, was für jeden Namen passieren soll, eingerückt sein.
> Sobald Code wieder auf der selben Einrückung wie vorher ist, verlassen wir die Schleife.


---

### "While" - Schleifen

Für den Fall, dass wir etwas mehrfach ausführen lassen wollen, ohne genau zu wissen wie oft nutzen wir `while` - Schleifen.
Mit ihnen können Codeblöcke ausgeführt werden, solange eine Bedingung erfüllt ist.

Die Syntax ist also sehr ähnlich zu `if` - Anweisungen:

```python
while name == "Steve":
	print("Das passiert, so lange, wie der Name 'Steve' bleibt")
```

---

### Das `break` Schlüsselwort

Nicht immer wollen wir, dass Schleifen bis zum Ende laufen.
Dann können wir `break` benutzen, um aus der Schleife auszubrechen.

```python
while name == "Steve":
	print("Das passiert, so lange, wie der Name 'Steve' bleibt")
	break
	print("Das hier wird nicht mehr ausgeführt")
```

---

## Referenz

### Vergleichsoperatoren

| Zeichen | Erklärung      | Beispiel                                             |
|---------|----------------|------------------------------------------------------|
| `==`    | ist gleich     | `3 == 3` => `True`, `'apfel' == 'birnen'` => `False` |
| `!=`    | ungleich       | `3 != 3` => `False`, `'apfel' != 'birnen'` => `True` |
| `<`     | kleiner als    | ``                                                   |
| `>`     | größer als     | ``                                                   |
| `<=`    | kleiner gleich |                                                      |
| `>=`    | größer gleich  |                                                      |

### Logische Operatoren

| Zeichen | Erklärung                                                              | Beispiel                                                  |
|---------|------------------------------------------------------------------------|-----------------------------------------------------------|
| `and`   | logisches **und**: beide Ausdrücke müssen zu `True` auswerten          | `True and True` => True, `'a' == 'b' and True` => `False` |
| `or`    | logisches **oder:** einer der beiden Ausdrücke muss zu `True` ausweren | `True or False` => `True`, `False or False` => `False`    |
| `not`   | Negation: kehrt einen Wahrheitswert um                                 | `not True` => `False`                                     |
