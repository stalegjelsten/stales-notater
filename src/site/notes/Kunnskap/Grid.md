---
{"dg-publish":true,"permalink":"/Kunnskap/Grid/","title":"Grid","tags":["css","it1"]}
---


# Grid

Grid er et layoutverktøy i [[Kunnskap/CSS\|CSS]]. Det kan brukes på samme måte som [[Kunnskap/Flexbox\|Flexbox]], men der flexbox er basert på en rad eller kolonne med bokser, er grid basert på et rutenett av bokser.

>[!tip] Flexbox vs grid
> Flexbox er svært god egnet for mindre layouter. Hvis du skal lage en layout for en hel nettside kan [[Kunnskap/Grid\|Grid]] være bedre egnet.
>
> Flexbox er også mye bedre egnet hvis du bare skal justere layout langs én akse.

## Enkel bruk av grid
For å lage et rutenett i et [[Kunnskap/HTML\|HTML]]-element er du nødt til å sette egenskapen `display: grid;` på det.

Deretter velger du hvor mange rader og kolonner du ønsker i rutenettet ved hjelp av `grid-template-rows` og `grid-template-columns`. Se eksempelet nedenfor.

<div class="rutenett" style="display: grid;grid-template-rows: 2rem 20vh max(3rem, 10vh);grid-template-columns: repeat(2, 1fr) 2fr; padding: 1rem; gap:0.2rem;">
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
	<div class="item" style="border-radius:0.1rem; background-color:rgba(20,200,20,0.3)"></div>
</div>

```css
div.rutenett {
  display: grid;
  grid-template-rows: 2rem 20vh max(3rem, 10vh);
  grid-template-columns: repeat(2, 1fr) 2fr;
}
```

I griden ovenfor har jeg definert tre rader med høydene
1. 2rem (vanligvis 32px, men det kommer an på skriftstørrelsesinnstillingene)
2. 20vh (20% av vindushøyden)
3. `max(3rem, 10vh)` gir oss den minste størrelsen av `3rem` og `25vh`. I praksis vil dette gjøre at den minste høyden på denne raden er `3rem`, mens den vanligvis er 10% av vindushøyden.

I tillegg har jeg definert tre kolonner med verdiene `repeat(2, 1fr) 2fr`. Det betyr at
- Vi skal repetere teksten `1fr` 2 ganger. Dette gir to kolonner med bredde 1fr
- `2fr` gir en tredje kolonne med bredde 2fr

`fr` er en brøkverdi som forteller hvor stor andel av den totale bredden kolonnene skal oppta. I vårt tilfelle har vi til sammen $1+1+2=4$ fr. Det betyr at 1fr tilsvarer 25% av bredden. Den siste kolonnen er `2fr`, eller 50% av bredden.
