---
{"dg-publish":true,"permalink":"/Kunnskap/Midtstille innhold/","title":"Midtstille innhold","tags":["it1","css"]}
---


# Midtstille innhold
{ #f26ba4}


Å midtstille en `div` eller annet innhold i både vertikal og horisontal retning gjøres på følgende måte:
{ #e58eb3}

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

![](https://i.imgur.com/Wy5c2Kb.jpeg)
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
