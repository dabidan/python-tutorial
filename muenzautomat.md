# Münzenrückgabe

## Aufgabe
Die Bahn hat Sie beauftragt, für ihre Automaten die Stückelung
des Wechselgelds zu ermitteln. Schreiben Sie eine Funktion, die
als Parameter den Munzvorrat als Wörterbuch und den rückzugebenden
Betrag erhält und die zurückzugebenden Münzen wieder als Wörterbuch
zurückgibt. Die Funktion "divmod" könnte nützlich sein, die sowohl
eine Ganzzahldivision durchführt und sowohl Quotient als auch
Rest zurückgibt. Wie würden Sie den Fall behandeln, wenn aus dem
Münzvorrat keine Ruckgabe möglich wäre.

## Lösung ohne Beachtung des Münzvorrats
Zur Vereinfachung wurden alle Geldbeträge in Cent angegeben.

```Python
def rueckgabe(betrag):
    zurueck = {}
    zurueck[200], rest = divmod(betrag, 200)
    zurueck[100], rest = divmod(rest, 100)
    zurueck[50], rest = divmod(rest, 50)
    zurueck[20], rest = divmod(rest, 20)
    zurueck[10], rest = divmod(rest, 10)
    zurueck[5], rest = divmod(rest, 5)
    zurueck[2], rest = divmod(rest, 2)
    zurueck[1] = rest
    return zurueck
```

An der Lösung fällt auf, dass fast gleiche Zeilen mehrfach wiederholt
werden. Das macht Programme nicht nur lang und schwer lesbar, sobald
sich etwas ändert (z.B. die Überprüfung, ob auch genug Münzen im
Vorrat sind), muß diese Änderung an vielen Stellen durchgeführt werden.
Dabei können sich lich Übertragungsfehler einschleichen.
Besser ist es, den sich wiederholenden Teil in einer for-Schleife zu
schreiben. Der sich ändernde Teil ist die Schleifenvariable:

```Python
def rueckgabe(betrag):
    stueckelung = [200, 100, 50, 20, 10, 5, 2, 1]
    zurueck = {}
    rest = betrag
    for cent in stueckelung:
        zurueck[cent], rest = divmod(rest, cent)
    return zurueck
```

## Lösung mit Beachtung des Münzvorrats
Wir wollen nun auch den Münzvorrat berücksichtigen. Es können maximal
so viele Münzen zurückgegeben werden, wie auch da sind. Dies berechnen
wir in 3 Schritten.

1. Mit // berechnen, wie viele Münzen wir eigentlich zurückgeben wollen.
2. Wenn dies mehr Münzen sind, als vorhanden, die Anzahl der zurückgegebenen Münzen entsprechend reduzieren.
3. Den Restbetrag berechnen.

```Python
def rueckgabe(muenzvorrat, betrag):
    stueckelung = [200, 100, 50, 20, 10, 5, 2, 1]
    zurueck = {}
    rest = betrag
    for cent in stueckelung:
        anzahl = rest // cent
        if anzahl > muenzvorrat[cent];
            anzahl = muenzvorrat[cent]
        zurueck[cent] = anzahl
        muenzvorrat[cent] = muenzvorrat[cent] - anzahl
        rest = rest - cent * anzahl
    if rest > 0:
        print("Rückgeld reicht nicht. Es bleiben {} Cent übrig".format(rest))
    return zurueck
```
