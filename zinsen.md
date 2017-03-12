# Tilgungsrechner

## Aufgabe
Sie haben sich ein gebrauchtes Auto für 4300€ gekauft. 800€ hatten Sie auf ihrem
Sparkonto, den Rest leihen Sie sich zu 0.5% Zinsen pro Monat. Jeden Monat zahlen
Sie 150€ zurück. Nach wie vielen Monaten sind Sie schuldenfrei? 

## Lösung
```Python
def anzahl_monate(gesamt_betrag, eigenanteil, tilgung, zinsen):
    rest_betrag = gesamt_betrag - eigenanteil
    monate = 0
    while rest_betrag > 0:
        rest_betrag = rest_betrag * (1 + zinsen) - tilgung
        monate = monate + 1
    return monate

# Hauptprogramm
gesamt_betrag = 4300
eigenanteil = 800
zinsen = 0.5 / 100
tilgung = 150
print("In", anzahl_monate(gesamt_betrag, eigenanteil, tilgung, zinsen),"Monaten bist Du Schuldenfrei.")
```
