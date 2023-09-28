# Variablen

Variablen sind Platzhalter. 
Sie ermöglichen uns unbekannte (oder nicht vollständig bekannte) Werte festzuhalten und zu verwenden.
Sie können beliebige Namen haben sofern sie **mit einem Buchstaben oder einem Unterstrich** beginnen und **nur alphanumerische Zeichen** oder den Unterstrich (a-z, A-Z, 0-9 und _) enthalten.

Man kann mithilfe einer Zuweisung der Variable einen Wert geben:

```python
name = "Steve"
```

Das kann ein expliziter Wert, wie in diesem Fall der String `"Steve"` oder 
auch einfach der Wert einer anderen Variable sein:

```python
a = 1
b = a
``` 

## Zuweisungen

Wie gerade schon gesehen, haben wir unseren Platzhaltern gerade Inhalt gegeben.
Das funktioniert in Python mit dem `=` Operator - das bedeutet der macht aktiv etwas!
In unserem Fall gibt er unserer Variable die auf seiner **linken** Seite steht den Wert, der auf der **rechten** Seite steht.
Auf der linken Seite stehen also immer* Variablen und auf der rechten Seite das, was ihr Inhalt werden soll.

```python
a = 1  # Das funktioniert
1 = 2  # Das funktioniert nicht!
```

> **Hinweis:** auf der rechten Seite dürfen nur Wohldefinierte Sachen stehen!

## Extras

Man kann auch mehrere Variablen in einer Zeile deklarieren:

```python
mein_name, dein_name, sein_name = "Steve A.", "Steve B.", "Steve"  # Vollkommen legitim
```
