# Beispiel: Zahlensysteme: Konvertierung von Zahlen zur Basis 6


## Aufgabe:
Entwerfen Sie einen Algorithmus, der eine Folge von Ziffern, die
eine Zahl zur Basis 6 darstellen sollen, in eine Zahl umwandeln soll.
Fängt der Algorithmus bei der niedrigsten oder höchsten Stelle an?
Wandeln Sie die Ziffern 3501 um und geben Sie alle Zwischenergebnisse
als Dezimalzahl an.

## Lösungweg

* Eingabe: Ein String mit Ziffern.
* Ausgabe: Eine Zahl.
* Verarbeitung: Die Darstellung einer Zahl zu einer Basis ergibt sich aus den Potenzen dieser Basis <i>b</i>.
  Aus den Ziffern <i>a<sub>0</sub></i>, <i>a<sub>1</sub></i>, <i>a<sub>2</sub></i>, <i>a<sub>3</sub></i> berechnet sich die Zahl `a = a_0 * b ^ 3 + a_1 * b ^ 2 + a_2 * b + a_3`.

Die direkte Übersetzung nach Python sähe so aus:
```python
def convert(number):
    result = int(number[0]) * 6 ** 3 + int(number[1]) * 6 ** 2 + int(number[2]) * 6 + int(number[3])
    return result

print("Ergebnis:", convert("3501"))
```

Diese „Lösung“ hat ein paar Nachteile. So ist sie auf Zahlen mit genau vier Ziffern beschränkt
und man muß an drei Stellen die `6` ändern, wenn man die Basis ändern will.
Da alle Summanden der Summe gleich aufgebaut sind, kann man sie in einer for-Schleife überführen.
Da die höchste Potenz von der Anzahl der Stellen abhängt, bestimmen wir die Länge des Strings `number`
mit der `len`-Funktion:

```python
def convert(number):
    result = 0
    power = len(number)
    for digit in number:
        power = power - 1
        result = result + int(number[0]) * 6 ** power
    return result
```

Durch geschicktes Umformen das oberen Ausdrucks, läßt sich sogar das Potenzieren vermeiden. Dazu
klammert man einfach `b` aus: `a = (((a_0 * b) + a_1 * b) + a_2) * b + a_3`
Oder als Python-Code

### Code
```python
def convert(number, base=6):
    result = 0
    for digit in number:
        result = result * base + int(digit)
        print("Zwischenergebnis:", result)
    return result

print("Ergebnis:", convert("3501"))
```

### Ausgabe
```text
Zwischenergebnis: 3
Zwischenergebnis: 23
Zwischenergebnis: 138
Zwischenergebnis: 829
Ergebnis: 829
```

(PS: diese Funktionalität gibt es auch schon fertig: `int("3501", 6)`)

