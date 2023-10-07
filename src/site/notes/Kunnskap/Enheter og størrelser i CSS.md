---
{"dg-publish":true,"permalink":"/Kunnskap/Enheter og størrelser i CSS/","title":"Enheter og størrelser i CSS","tags":["css","it1"]}
---


# Enheter og størrelser i CSS
Når vi skal definere størrelsen til HTML elementer så bruker vi lengdeenheter. Den klassiske måten å angi størrelse på dataskjermer er å bruke piksler (`px`), men dette kan medføre problemer dersom nettsidene skal være [[Kunnskap/Universell utforming av nettsider\|universell]].

>[!tip] 62.5%-trikset gjør det enklere å regne ut størrelser
>I læreboka Kode 1 så anbefaler forfatterne å bruke 62.5%-trikset. Dette trikset gjør at `1rem` får den samme størrelsen som `10px` for alle brukere med standard tekststørrelse.
>
> Hvis du skal sette inn et element med bredden 600px så kan du nå skrive 60rem i stedet, og dette vil fungere bra både for dem som har standard tekststørrelse og dem som har valgt en annen tekststørrelse.
>
>```css
>html {
>	font-size: 62.5%; /* gjør tekststørrelsen tilsvarende 10px */
>}
>body {
>	font-size: 162%; /* setter opp tekststørrelsen igjen til standard */}
>}
>```
>
> I trikset utnytter vi at $\frac{1}{0.625}=1.62$ og at `rem` er definert ut fra tekststørrelsen til HTML-typeselektoren. Siden hele `body` har fått størrelse 162% så blir egentlig tekststørrelsen i body: $62.5 \%\cdot 162\%=100\%$.

## Ulike typer enheter

### Piksler
En piksel er en absolutt enhet, og hver piksel er et bildepunkt på skjermen.[^1] En stor PC skjerm er i dag gjerne *4K*, eller 3840px × 2160px. 

I de fleste tilfeller er det lurt å unngå å bruke piksler.

### cm
Centimeter er også en absolutt enhet. Hver cm er omtrent 37,8 piksler.

### em
En `em` tilsvarer bredden av bokstaven `m` med aktuell skrifttype og skriftstørrelse til HTML-elementet den tilhører. Siden størrelsen av en `em` avhenger av både skrifttype og -størrelse så er dette en relativ enhet.

Hvis du bruker `em` i en overskrift så vil 1em tilsvare bredden på en `m` i fonten i overskriften.

### rem
En `rem` (relativ em) tilsvarer bredden av bokstaven `m` med skrifttypen og skriftstørrelsen til `html`-taggen i CSS. Rem er en relativ enhet.

Hvis du bruker `rem` i en overskrift så vil 1rem tilsvare bredden på en `m` i fonten definert i `html`-selektoren.

### prosent (%)
Prosent er en relativ enhet som er relativ til størrelsen av til HTML forelderen. Et [[Kunnskap/Display inline, block og inline-block\|blokkelement]] med `width: 50%` vil ta opp halvparten av bredden til forelderen.

## Eksempler
I dette eksempelet ser vi hvordan 2em og 2rem gir svært ulike paddinger over og under overskriftsteksten. Teksten i `html` settes til 62,5%. Dette er et triks som gjør at `1rem = 10px` i de fleste tilfeller. Vi kan dermed bruke rem istedenfor piksler, og enkelt gjøre det mulig å regne ut størrelsen på ulike elementer.

<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="yLGEwVZ" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/yLGEwVZ">
Demo av em og rem</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>

[^1]: På nyere PCer og Macer er det vanlig at man slår sammen noen av de fysiske pikslene på skjermen. En PC som er stilt inn til å vise skjermen på 150 % størrelse (ganske vanlig) vil dermed bruke 3 fysiske piksler for hver virtuelle piksel.
