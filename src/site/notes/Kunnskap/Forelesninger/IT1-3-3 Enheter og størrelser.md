---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-3-3 Enheter og størrelser/","title":"IT1-3-3 Enheter og størrelser","tags":["it1","forelesning"]}
---

	
# IT1-3-3 Enheter og størrelser
Kapittel 3.3
9\. okt 2023

Vi trenger ofte å bestemme størrelsen på HTML-elementer. Det gjør vi med CSS-egenskaper som `font-size`, `width` og `height`. Vi kan bruke måleenheter som `cm` i CSS, men det er ofte et dårlig valg. I dag skal vi se på hvorfor.

## Læringsmål
- Forklare hva piksler, `rem`, `vh` og `vw` er
- Bruke `px`, `rem`, `%`, `vh` og `vw` til å utforme nettsider

---

## Plan framover

| Uke | Dato        | Fagstoff                      |
| --- | ----------- | ----------------------------- |
| 41  | man. 9.10   | 3.3 Størrelser og enheter     |
| 41  | tors. 12.10 | 3.5 Flexbox                   |
| 42  | man. 16.10  | 3.6 Grid                      |
| 42  | tors. 19.10 | Hjemmeoppgave flexbox og grid |
| 43  | man. 23.10  | Flexbox og grid               |
| 43  | ons. 25.10  | Fagdag                        |

---

### Absolutte lengdeenheter
De absolutte lengdeenhetene er knyttet til bildepunktene (pikslene) på skjermen som viser innholdet. 
* elementer vil se store ut på skjermer med lav oppløsning (få piksler)
* elementer vil se små ut på skjermer med høy oppløsning (mange piksler)
* *Du bør unngå å bruke absolutte lengdeenheter siden disse ikke tar hensyn til brukerens skriftinnstillinger*.
* Eksempler: piksler, cm, punkter

#### Piksler
En piksel er en absolutt enhet, og hver piksel er et bildepunkt på skjermen. En stor PC-skjerm er i dag gjerne 3840px × 2160px (også kalt *4k*).

![bg right:30%](https://media.printables.com/media/prints/484522/images/3957848_ba687bfc-d606-4f7e-918f-8cd3a039f2e7/thumbs/inside/1600x1200/png/pixelart-pikachu-v1_1.webp)

---

### Relative lengdeenheter
Relative enheter tar utgangspunkt i en annen størrelse og bruker dette som referanse.

<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="vYvvbOZ" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/vYvvbOZ">
	Demo av absolutte og relative størrelser</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

#### em og rem
- En `em` tilsvarer bredden av bokstaven `m` med aktuell skrifttype og skriftstørrelse til HTML-elementet den tilhører. 
- En `rem` (relativ em) tilsvarer bredden av bokstaven `m` med skrifttypen og skriftstørrelsen til `html`-taggen i CSS.

---

#### prosent (%)
Prosent er en relativ enhet som er relativ til størrelsen av til HTML forelderen. Et blokkelement med `width: 50%` vil ta opp halvparten av bredden til forelderen.

<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="vYvvbOZ" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/vYvvbOZ">
	Demo av absolutte og relative størrelser</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

---

#### vh og vw
- Viewport height `vh` er en relativ enhet til størrelsen av nettleservinduets høyde. `40vh` vil tilsvare 40 % av nettleserens høyde.
- Viewport width `vw` er en relativ enhet til størrelsen av nettleservinduets bredde. `40vw` vil tilsvare 40 % av nettleserens bredde.

<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="vYvvbOZ" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/vYvvbOZ">
	Demo av absolutte og relative størrelser</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

---

## Samkoding hvor vi bruker ulike størrelser
Åpne VS code og lag en ny mappe `41-piksler-og-rem`
* Bruke emmet til å lage strukturen. En `container` med tre `div` inni.
* Gi hver av de tre `div`ene en klasse: `pikselStorrelse`, `remStorrelse`, `emStorrelse`
* Gi hver `div` en kantlinje og litt marger
* Legge inn css for `pikselStorrelse`, `remStorrelse`, `emStorrelse`
* Legg inn `font-size` på html og div for å vise forskjellen på `em` og `rem`
* Legg inn halv bredde på en `div`
* Legg inn `vh` på `height` og `min-height`

---

## Skriv forklaringer for deg selv
Du har nå sett hvordan ulike lengdeenheter brukes. Skriv forklaringer til deg selv (i OneNote, Notion, Notater eller Word) angående følgende temaer:

1. Hva er standard tekststørrelse hos en nettleser (i piksler)?
2. Forklar hvorfor vi bør bruke en relativ måleenhet når vi bestemmer tekststørrelsen?
3. Forklar hvordan du kan få et element til å ta opp høyden til 50 % av nettleservinduet?
4. Forklar hvordan du kan bruke flere klasser på ett HTML-element
5. Forklar hvordan du kan bruke *Emmet* til å lage flere `div` elementer med ulike klasser
6. Vi skal først og fremst bruke disse enhetene i IT1: `px`, `rem`, `%`, `vh` og `vw`. Skriv en kort forklaring til hver av dem.

---

## Kod selv: Lag en nettside basert på denne Wireframen

![h:550](https://stalegjelsten.github.io/IT1/00-bilder/Wireframe%20CSS%20enheter%20og%20størrelser.png)
