---
{"dg-publish":true,"permalink":"/Kunnskap/Display inline, block og inline-block/","title":"Display inline, block og inline-block","tags":["it1","css"]}
---


# Display inline, block og inline-block
Alle HTML-elementer har en default display type. De aller fleste elementer er av typen block. Et block element vil ta opp 100 % av bredden til sitt foreldreelement, og det vil alltid legges til et linjeskift før og etter block elementet.

F.eks er alle overskrifter `display: block`.
<h2 style="background-color: lightyellow">Egen overskrift</h2>

Inline elementer vil derimot ikke ta opp mer plass enn nødvendig på den nåværende linja, og de vil heller ikke generere noen automatiske linjeskift. **Fet skrift** eller [lenker](https://stales-notater.vercel.app) er to eksempler på inline elementer.

Vi kan endre på display-typen til et element ved hjelp av disse CSS-kodene
```css
h1 { display: inline }
img { display: inline-block }
a { display: block }
```

## Inline-block
Inline-block er en spennende mellomting mellom inline og block. Den gir oss mulighet til å lage elementer med en gitt bredde og høyde. Her viser jeg med to ulike `h2` med `display: inline-block`

```css
<h2 style="display: inline-block; width: 30%; background-color: lightyellow">Test</h2><h2 style="display: inline-block; width: 30%; background-color: lightblue">Test</h2>
```

<h2 style="display: inline-block; width: 30%; background-color: lightyellow">Test</h2><h2 style="display: inline-block; width: 30%; background-color: lightblue">Test</h2>
