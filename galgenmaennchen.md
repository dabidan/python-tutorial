# Galgenmännchen
Schreiben Sie ein Spiel, bei dem ein Wort geraten werden soll. Zu Anfang wird
fur jeden Buchstaben ein `_` ausgegeben. Nun werden nacheinander Buchstaben
eingelesen (`input`). Das Wort wird erneut mit den richtig geratenen Buchstaben
ausgegeben. Für jeden Buchstaben, der nicht im Wort vorkommt, bekommt man
einen Fehlerpunkt. Wird das komplette Wort geraten, hat man gewonnen, bei 7
Fehlerpunkten verloren. Nutzen Sie `choice` aus dem Modul `random` um aus einer
vorgegebenen Wörterliste eines auszuwählen.

# Lösungsweg
Zuerst der grobe Ablauf des Spiels:

1. Auswahl des zu ratenden Wortes
2. Darstellen des Wortes mit `_`.
3. Abfrage eines Buchstabens.
4. Wenn Buchstabe nicht im Wort, Fehlerpunkte erhöhen.
5. Wenn Fehlerpunkte bei 7 --> verloren
6. Darstellen des Wortes mit `_` und den geratenen Buchstaben
7. Wenn das Wort komplett ist --> gewonnen
8. Gehe zu 3.

Wir haben nun die Aufgabe in eine etwas formalere Sprache übersetzt.
Ist das Spiel mit den Anweisungen spielbar? Halte Dich genau an die
Wenn eine Anweisung unklar ist, oder fehlt, korrigiere den Ablauf.

Der nächste Schritt ist, die Anweisungen in Funktionen aufzuteilen
und Eingabe- und Ausgabeparameter zu identifizieren. Gibt es Anweisungen,
die noch feiner unterteilt werden müssen?

# Das Spiel
Die Hauptfunktion ist ein Spieldurchlauf. Eingabe wäre ein Wort und die Ausgabe ob gewonnen oder nicht.
Das was übrig bleibt, ist, ein Wort auszusuchen und auszugeben ob gewonnen wurde:
```Python
import random
wortliste = ["Lokführermütze", "Apfelsaft", "Rhythmus"]

wort = random.choice(wortliste)
gewonnen = spiel(wort)
if gewonnen:
    print("Du hast gewonnen!")
else:
    print("Du hast leider verloren!")
```
