---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-2-4 Oppsummering av 90-tallsnettsider/","title":"IT1-2-4 Oppsummering av 90-tallsnettsider","tags":["it1","forelesning"]}
---


# IT1-2-4 Oppsummering av 90-tallsnettsider

IT1 2023-09-21

## Plan for dagen

- Læringspunkter fra nettsidene
- Lære fargeforløpning i CSS
- Lage «magisk tekst»-effekten

<p class="codepen" data-height="300" data-default-tab="result" data-slug-hash="KKBPMYE" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/KKBPMYE">
	Magic text</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

---

## Læringspunkter fra nettsider
Finn ut hvilke av disse punktene du har syndet mot. Diskuter med sidemannen og skriv ned en begrunnelse for hvorfor punktet er viktig.

1. Lag en egen mappe til prosjektet. Bruk filnavn uten æ, ø, å eller mellomrom
2. Lag en `index.html`
3. **Lagre** alle filer før du leverer
4. `<html lang="no">`
5. Ikke last inn flere fonter enn nødvendig
6. **Husk `ALT`-tekst**

---

## Fargeforløpninger / gradienter

<div style="background: linear-gradient(90deg, #a050e8 0%, #00ff88 50%, #ff00ff 100%); aspect-ratio: 8/1; border-radius: 1vw;">&nbsp;</div>

En fargeforløpning er en gradvis overgang mellom ulike farger. Boksen ovenfor er en `div` som viser en lineær forløpning fra lilla til turkis og tilbake til lilla.

```css
div {
	background: linear-gradient(90deg, #a050e8 0%, #00ff88 50%, #ff00ff 100%); 
	aspect-ratio: 8/1; 
	border-radius: 1vw;
}
```

[Fargeløpninger i CSS hos Ståles notater](https://stales-notater.vercel.app/Kunnskap/Fargeforl%C3%B8pninger%20i%20CSS/)

---
Ved å skrive `linear-gradient` får vi en lineær (rettlinjet) forløpning. Inne i parentesen etter `linear-gradient` har jeg lagt inn følgende parametere
- `90deg` for at forløpningen skal gå i en rett linje fra venstre mot høyre
- `#a050e8 0%` definerer at fargen `a050e8` skal ha være på sitt sterkeste helt ved starten av forløpningen
- `#00ff88 50%` definerer at fargen `00ff88` skal ha være på sitt sterkeste ved midten av forløpningen
- `#ff00ff 100%` definerer at fargen `a050e8` skal ha være på sitt sterkeste (igjen) helt på slutten av forløpningen
- `aspect-ratio: 8/1` gjør at boksens høyde blir 1/8 av bredden. Jeg kunne også satt en høyde med `height`, men på denne måten så ser boksen ganske lik ut i ulike skjermoppløsninger.
- `border-radius: 1vw` gir avrundede hjørner. Ved å bruke *viewport width* enheter så blir størrelsen på avrundingen avhengig av skjermstørrelsen.

---

## Tekst med fargeforløpning
Å farge tekst med en fargeforløpning gir en stilig effekt (men den bør brukes med forsiktighet – nettsiden bør alltid være godt lesbar!)

<h3 style="background-image: linear-gradient(15deg, #a050e8 0%, #00ff88 55%, #a050e8 100%); -webkit-background-clip: text; -webkit-text-fill-color: transparent;">Demonstrerer fargeforløpning i tekst</h3>

### Eksempel på bruk
```css
h3 {
	background-image: linear-gradient(15deg, #a050e8 0%, #00ff88 65%, #a050e8 100%);
	background-clip: text;
	-webkit-background-clip: text;
	-webkit-text-fill-color: transparent;
}
```

[Fargeløpninger i CSS hos Ståles notater](https://stales-notater.vercel.app/Kunnskap/Fargeforl%C3%B8pninger%20i%20CSS/)

---
For å lage tekst med en fargegradient så kan du bruke CSS til å 
- legge til en gradient som et bakgrunnsbildet på HTML elementet
- clippe bakgrunnen til akkurat det området der teksten er. Dessverre er `background-clip` en uoffisiell CSS-egenskap. For at den skal virke i de fleste nettlesere må du derfor bruke både `background-clip` og `-webkit-background-clip`.
- bruke en transparent farge på skriften for å se bakgrunnen bak

>**OBS!** Bruk en fallback bakgrunnsfarge!
>Siden det ikke er absolutt alle nettlesere som kan vise fargeforløpninger på tekst så er det lurt å legge til `background-color: FARGENAVN` *før* `background-image: linear-gradient()`. Hvis nettleseren ikke klarer å vise fargeforløpningen kan den da vise fargen du har definert i `background-color`.

---

## Magisk tekst

<p class="codepen" data-height="300" data-default-tab="result" data-slug-hash="KKBPMYE" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/KKBPMYE">
	Magic text</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

[Magisk tekst hos Ståles notater](https://stales-notater.vercel.app/Kunnskap/Magisk%20skinnende%20tekst%20med%20CSS/)
