---
{"dg-publish":true,"permalink":"/Kunnskap/Flexbox/","title":"Flexbox","tags":["it1","css"]}
---


# Flexbox
`Flexbox` er en måte vise elementer i rader eller kolonner med [[Kunnskap/CSS\|CSS]]. 

Du lager en `flexbox` ved å skrive `display: flex;` i CSS-koden til HTML elementet. Alle elementer inni flexboxen blir automatisk `flex items`.

>[!tip] Flexbox vs grid
> Flexbox er svært god egnet for mindre layouter. Hvis du skal lage en layout for en hel nettside kan [[Grid\|Grid]] være bedre egnet.

## Eksempler
Eksempelet under er bygget opp av en hoved`div` (flexboxen) med blå farge. Inne i flexboxen ligger det 4 nye diver, som blir *flex items* til flexboxen. Se CSS-koden lenger nede.

<section style="display: flex; background-color: blue; height: 5rem; gap: 1rem; padding: 1rem; font-size: 30px;"><div style="background-color: darkgreen; display: flex; justify-content: center; align-items: center; flex: 1;">Item 1</div><div style="background-color: darkgreen; display: flex; justify-content: center; align-items: center; flex: 1;">Item 2</div><div style="background-color: darkgreen; display: flex; justify-content: center; align-items: center; flex: 1;">Item 3</div><div style="background-color: darkgreen; display: flex; justify-content: center; align-items: center; flex: 1;">Item 4</div></section>

```css
div.container {
	display: flex;
	background-color: blue;
	height: 5rem; /* for å gi boksen en høyde */
	gap: 1rem; /* mellomrom mellom items */
	padding: 1rem; /* for å vise boksen bedre */
	font-size: 30px;
}
div.item {
	background-color: darkgreen;
	display: flex; /* for å kunne midtstille teksten "Item 1" */
	justify-content: center; /* midtstiller langs hovedaksen */
	align-items: center; /* midtstiller langs tverraksen */
	flex: 1; /* alle items skal være like store */
}
```

### Ulike typer flexboxer
<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="XWoOjrq" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/XWoOjrq">
	Demo av Flexbox</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

## Akser
Flexbox vil som standard velge den horisontale aksen som hovedakse (*main axis*) og legge flex items bortover langs denne. Den vertikale aksen vil dermed gå på tverrs og kalles på engelsk for *cross axis*.

Vi kan bytte akse ved å bruke `flex-direction: column;`. Dersom vi ønsker å ha motsatt rekkefølge på elementene i flexboxen bruker vi `flex-direction: row-reverse;` eller `flex-direction: column-reverse;`.

## Huskeliste flexbox

| CSS             | Forklaring                                                                       |
| --------------- | -------------------------------------------------------------------------------- |
| display: flex   | Gjør elementet til en flexbox                                                    |
| justify-content | Justerer flex items langs hovedaksen til flexboxen                               |
| gap             | Mellomrom mellom flex items                                                      |
| align-items     | Justerer flex items på tvers av hovedaksen                                       |
| flex-direction  | Velger hovedakse og retning for hovedaksen                                       |
| flex-wrap       | Angir om items skal legge seg på en ny linje dersom det ikke er plass til dem    |
| flex            | Settes på flex items. Et tall som forteller hvor stort dette elementet skal være |
| order           | Settes på flex items. Et tall som påvirker rekkefølgen til itemet. Standard er `order: 0;` |



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/midtstille-innhold/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">





# Midtstille innhold
Å midtstille en `div` eller annet innhold i både vertikal og horisontal retning gjøres på følgende måte:
1. Bruk `display:flex;` på forelderen til elementet du ønsker å midtstille
2. Bruk deretter `justify-content: center;` og `align-items: center;` for å midtstille innholdet langs begge akser.

<div style="height:4rem; background-color: purple; display:flex; justify-content: center; align-items:center;"><div style="background-color: hotpink">This text is centered</div></div>

```css
.container {height:4rem; background-color: purple; display:flex; justify-content: center; align-items:center;}
.centered {background-color: hotpink}
```

## Historikk
Å midtstille en div ble lenge (spøkefullt) betegnet som noe av det vanskeligste man kunne gjøre i [[Kunnskap/CSS\|CSS]].

![Meme som viser Boromir fra Ringenes Herre som sier "One does not simply center a div"](https://miro.medium.com/v2/resize:fit:1100/format:webp/1*rf4QAy4yYPdfuLsZ7NrHZA.jpeg)

>[!quote]- ChatGPT forklarer hvorfor det var vanskelig å midtstille diver
>Spørsmål: Hvorfor var det så vanskelig å midtstille en div før flexbox?
>
>**ChatGPT**: Før introduksjonen av Flexbox og andre moderne layoutteknikker i CSS, ble det ansett som vanskelig å midtstille en `<div>` eller andre elementer innenfor sin foreldercontainer hovedsakelig på grunn av begrensningene i den tradisjonelle CSS-layoutmodellen, som kalles "Boksemalen" (Box Model).
> 
> Her er noen grunner til hvorfor midtstilling var utfordrende før Flexbox:
> 
> 1. Begrenset midtstillingsmuligheter: Tradisjonelle metoder for midtstilling, som å bruke `margin: auto;`, `text-align: center;`, og `vertical-align` for inline- eller inline-block-elementer, hadde ulike begrensninger og var ikke egnet for alle typer innhold og layouter. Disse var primært utviklet for tekst eller inline-elementer og var mindre fleksible for komplekse design.
> 
> 2. Komplekse arbeidsmetoder: Å oppnå horisontal og vertikal midtstilling krevde ofte komplekse og ikke-intuitive arbeidsmetoder som involverte bruk av absolutt posisjonering, negative marginer og faste dimensjoner. Slike løsninger var ofte skjøre og kunne bryte når innholdet eller containerstørrelsen endret seg.
> 
> 3. Fluktuer og clearfix: Fluktuer, som var vanlig brukt for å lage flersøylenlayouter, gjorde midtstilling mer utfordrende. For å midtstille elementer innenfor en fluktuerende forelder, var det ofte nødvendig å bruke tilleggs clearfix-teknikker for å sikre at containeren ville utvides for å inneholde barneelementene riktig.
> 
> 4. Manglende ekte vertikal midtstilling: Å oppnå vertikal midtstilling var spesielt vanskelig før Flexbox, da det ikke fantes en enkel måte å midtstille et element både horisontalt og vertikalt innenfor sin forelder på. CSS ga ikke en enkel mekanisme for dette formålet.
> 
> 5. Inkompatibilitet mellom nettlesere: Forskjellige nettlesere implementerte CSS-egenskaper og layoutmodeller forskjellig, noe som førte til utfordringer med kryss-nettleserkompatibilitet når man prøvde å midtstille elementer. Dette betydde at det som fungerte i én nettleser kanskje ikke fungerte i en annen.
> 
> 6. Utfordringer med responsiv design: Å midtstille elementer i responsive design, der container- og innholdsstørrelser endres avhengig av skjermstørrelsen, var spesielt problematisk. Mange tradisjonelle metoder brøt sammen i responsive layouter.
> 
> Flexbox og CSS Grid forbedret situasjonen betydelig ved å tilby et kraftigere og mer forutsigbart layoutsystem. Med Flexbox kan du enkelt midtstille elementer både horisontalt og vertikalt, og det kan tilpasse seg ulike innholds- og containerstørrelser uten komplekse arbeidsmetoder. Disse moderne layoutteknikkene har gjort webutvikling mer tilgjengelig og forenklet prosessen med å midtstille elementer i CSS, og har eliminert mange av utfordringene utviklere tidligere møtte.


</div></div>
