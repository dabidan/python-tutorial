# Zahlensysteme zur Basis 6


## Aufgabe:
Entwerfen Sie einen Algorithmus, der eine Folge von Ziffern, die
eine Zahl zur Basis 6 darstellen sollen, in eine Zahl umwandeln soll.
Fängt der Algorithmus bei der niedrigsten oder höchsten Stelle an?
Wandeln Sie die Ziffern 3501 um und geben Sie alle Zwischenergebnisse
als Dezimalzahl an.

## Lösungweg

* Eingabe: Ein String mit Ziffern.
* Ausgabe: Eine Zahl.
* Verarbeitung: Die Darstellung einer Zahl zu einer Basis ergibt sich aus den Potenzen dieser Basis.
Aus den Ziffern a_3, a_2, a_1, a_0 berechnet sich die Zahl a = a_3 * b ^ 3 + a_2 * b ^ 2 + a_1 * b + a_0.

### Code
```python
def convert(number):
    result = 0
    for digit in number:
        result = result * 6 + int(digit)
        print(result)
    return result

print("Ergebnis:", convert("3501"))
```

## Ausgabe
```text
3
23
138
829
Ergebnis: 829
```

