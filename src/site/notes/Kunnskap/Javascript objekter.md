---
{"dg-publish":true,"permalink":"/Kunnskap/Javascript objekter/","title":"Javascript objekter","tags":["it","it1","javascript"]}
---


# Javascript objekter
Et objekt i [[Javascript\|Javascript]] er en samling av egenskaper og verdier. For eksempel kan objektet `bil` være definert på følgende måte

```javascript
let bil = {merke: "Audi", modell: "A3 Quattro", motorvolum: 2.0, eiere: ["Ståle Gjelsten", "Navn på tidligere eier"]}
```

Her har objektet `bil` nøklene `merke`, `modell`, `motorvolum` og `eiere`. Legg merke til at disse nøklenes verdier kan ha ulike datatyper.

For å hente fram verdien av en egenskapen `motorvolum` kan vi bruke `bil.motorvolum`. For eksempel vil `bil.motorvolum * 3` gi svaret `6` siden `2.0 * 3 = 6`. Det er også mulig å bruke syntaksen `bil["motorvolum"]` for å hente fram motorvolumet.

Vi kan også endre på verdiene eller legge til nye egenskaper på samme måte. Dersom vi også vil legge til en egenskap med registreringsår så kan vi gjøre:

```javascript
bil.registreringsaar = 2012
```

## Metoder
En metode er en funksjon lagret som egenskapen til et objekt.

```javascript
let bil = {merke: "Audi", modell: "A3 Quattro", slaaSammenMerkeOgModell() {return this.merke + " " + this.modell}}
```

Hvis man kaller metoden med `bil.slaaSammenMerkeOgModell()` så vil `Audi A3 Quattro` bli returnert. Legg merke til at vi ikke trenger noen kolon etter navnet på metoden.
