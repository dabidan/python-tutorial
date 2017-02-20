# Übersicht

## Grundstruktur

| Befehl        | Python          | Beschreibung |
|:-------------|:------------------|:------|
| a := b + c        | a = b + c | Weise der Variable _a_ einen neuen Wert zu.  |
| solange _Bedingung_: | while _Bedingung_: | Wiederhole nachfolgenden Block, solange die Bedingung erfüllt ist.  |
| für alle a von 1 bis n: | for a in range(1, n+1): | Wiederhole nachfolgenden Block für jede Zahl a von 1 bis n.   |
| wenn _Bedingung_:   | if _Bedingung_: | Führe nachfolgenden Block nur aus, wenn die Bedingung erfüllt ist.  |
| sonst:         | else: | Führe Block aus, falls die vorherige Bedingung nicht erfüllt ist. |
| definiere Funktion(a, b): | def function(a,b): | Definiere eine Funktion mit den Eingabeparametern a und b. |
| Ergebnis a | return a | Beende die Funktion und gib als Ergebnis a zurück. |

## Operatoren
Es gelten die üblichen mathematischen Operatoren `+`, `-`, `*`, `/`, `**` (Potenzieren)
und die Vergleichsoperatoren `==` (gleich), `!=` (ungleich), `<`, `>`, `<=`, `>=`.

## einfache Objekte
Einfache Objekte wie Zahlen (Ganzzahlen `235` und Kommazahlen `543.4`) und Zeichenketten `"Hallo!"`
sind unveränderlich. Rechenoperatoren wie `a + b` erzeugen ein neues Objekt mit einem neuen Wert.

## komplexe Objekte
Komplexe haben eine interne Struktur, die sich verändern kann. Beispiele sind Listen oder Wörterbücher.

### Listen
Listen sind eine geordnete Sammlung von Objekten.

| Code         | Beschreibung |
|:-------------|:------------------|
| a = [1, 2, 3]    | Erzeugt eine Liste mit drei Elementen |
| b = a[0]         | Ergibt das erste Element.      |
| b = a[-2]        | Ergibt das vorletzte Element.  |
| b = a[1:4]   | Neue Liste mit dem 2., 3. und 4. Element |
| a.append(7)  | Hängt ein Element an die Liste an. |
| b = a.pop()      | Entnimmt das Letzte Element der Liste. |
| b in a       | Prüft ob b in der Liste a enthalten ist. |
| a.remove(5)  | Entfernt das erste vorkommen des Elements aus der Liste |
| b = a.count(3) | Zählt, wie oft das Element in der Liste ist. |
| for b in a:  | Wiederholt den nachfolgenden Block mit jedem Element der Liste. |

### Wörterbücher
Ein Wörterbuch ist eine ungeordnte Sammlung von Schlüsseln. Jedem Schlüssel wird ein Wert zugeordnet. 

| Code         | Beschreibung |
|:-------------|:------------------|
| a = {"a": 3, "b": 7}    | Erzeugt ein Wörterbuch mit zwei Schlüsseln |
| b = a["a"]         | Gibt den Wert zum Schlüssel `"a"`.      |
| a[8] = "b"  | Weißt einem Schlüssel einen Wert zu. |
| del a["b"]     | Entfernt den Schlüssel. |
| b in a       | Prüft ob b in im Wörterbuch a enthalten ist. |
| for b in a:  | Wiederholt den nachfolgenden Block mit jedem Schlüssel aus dem Wörterbuch. |


