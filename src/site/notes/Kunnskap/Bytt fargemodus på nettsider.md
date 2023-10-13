---
{"dg-publish":true,"permalink":"/Kunnskap/Bytt fargemodus på nettsider/","title":"Bytt fargemodus på nettsider","tags":["it1","svelte","css"]}
---


# Bytt fargemodus på nettsider
Det er lurt å tilby brukeren å kunne bytte fargemodus på nettsidene dine, fra lys bakgrunn til mørk bakgrunn og tilbake igjen. Dette er i tråd med [[Kunnskap/Universell utforming av nettsider\|Universell utforming av nettsider]]. Pass på å ha god nok kontrast mellom tekst og bakgrunn, både i lys modus og mørk modus.

## Enkel løsning med Svelte
Dette er et eksempel på en enkel løsning i [[Kunnskap/Svelte\|Svelte]] hvor vi endrer på tekstfarge, bakgrunnsfarge, lenkefarge og en uthevingsfarge (engelsk: accent color) ved å trykke på en knapp. 

>[!warning] Preferanser blir ikke lagret
>Denne løsningen lagrer ikke brukerens preferanse noe sted. Dermed vil brukeren bli servert standard fargemodus når hen oppdaterer siden eller kommer tilbake til nettstedet ved en senere anledning.

### HTML
La oss først opprette knappen i [[Kunnskap/HTML\|HTML]]
```html
<button on:click={switchTheme} aria-label="bytt fargemodus">Bytt fargemodus!</button>
```

- `on:click={}` brukes i Svelte for å fortelle hva som skjer når vi trykker på et element
- `switchTheme` er navnet på javascriptfunksjonen for å endre på fargene
- `aria-label` er for at skjermlesere skal vite hva knappen gjør. Denne attributten er ikke nødvendig i eksempelet over, for her har vi allerede gitt knappen teksten *Bytt fargemodus!*. Dersom knappen ikke inneholder tekst (for eksempel kan du ha lyst til å bruke emojien ☀ for å endre modus) så *må* du legge til en aria-label.

### CSS
For å implementere bytte av bakgrunnsfarge i [[Kunnskap/Svelte\|Svelte]] med en knapp bør du definere fargene som [[Kunnskap/CSS variabler\|CSS variabler]]. Variablene defineres med to bindestreker før navnet, og brukes ved å skrive `var(--variabelnavn)`.

I koden nedenfor har jeg brukt `:global(body)` for å fortelle Svelte at vi skal endre på body-elementet. Hvis du skriver CSS-kode uten å bruke Svelte, så trenger du kun å skrive `body`.

```css
:global(body) {
	--text-color: black;
	--bkg-color: white;
	--nav-color: blue;
	--accent-color: hsl(206, 60%, 43%);
}
:global(body.dark-theme) {
	--text-color: white;
	--bkg-color: black;
	--nav-color: rgb(192, 76, 76);
	--accent-color: hsl(206, 60%, 61%);
}
:global(body) {
	background: var(--bkg-color);
	color: var(--text-color);
	font-family: Helvetica, Arial, sans-serif;  }
a {
	color: var(--nav-color);
}
```

Legg merke til at jeg har laget en klasse til `body` for den mørke modusen. 

### Javascript
I javascript så oppretter vi en ny funksjon kalt `switchTheme` som veksler mellom å aktivere og deaktivere klassen `dark-theme` på denne måten

```javascript
const switchTheme = () => {
	document.body.classList.toggle("dark-theme");
};
```

### Samlet Sveltekode
Koden nedenfor er komplett Sveltekode for en knøttliten nettside hvor man kan endre tema.

```svelte
<script>
  const switchTheme = () => {
    document.body.classList.toggle("dark-theme");
  };
</script>

<h1>Test</h1>
<p>Tester en lenke til <a href="https://nrk.no">nrk</a></p>
<button aria-label="bytt fargemodus" on:click={switchTheme}
  >Bytt fargemodus</button
>

<style>
  :global(body) {
    --text-color: black;
    --bkg-color: white;
    --nav-color: blue;
    --accent-color: hsl(206, 60%, 43%);
  }
  :global(body.dark-theme) {
    --text-color: white;
    --bkg-color: black;
    --nav-color: rgb(192, 76, 76);
    --accent-color: hsl(206, 60%, 61%);
  }
  :global(body) {
    background: var(--bkg-color);
    color: var(--text-color);
    font-family: Helvetica, Arial, sans-serif;
  }
  a {
    color: var(--nav-color);
  }
</style>
```
