---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-6-6 Webkamera med gif og localstorage/","title":"IT1-6-6 Webkamera med gif og localStorage","tags":["it1","forelesning"]}
---


# IT1-6-6 Webkamera med gif og localStorage

IT1 2024-01-29
- Oppfylle et løfte fra januar 2023
- localStorage: lagring av informasjon i nettleseren

---

## Javascript-kode for webkamera

```js
let videoObjekt = null;
let laster = false;
let videoBredde = 720;
$: videoHoyde = Math.floor((videoBredde * 9) / 16);

const hentWebkamera = async () => {
  laster = true;
  const stream = await navigator.mediaDevices.getUserMedia({
    video: { width: videoBredde, height: videoHoyde },
  });
  videoObjekt.srcObject = stream;
  videoObjekt.play();
  laster = false;
};
```

---

## HTML-kode for å vise webkamera

```html
{#if laster}
<h1>Laster webkamera...</h1>
{/if}
<!-- svelte-ignore a11y-media-has-caption -->
<video bind:this="{videoObjekt}" />
<button on:click="{hentWebkamera}">Vis webkamera</button>
```

---

## Endre størrelse på webkamera

```html
<p>
  Bredde: {videoBredde} <br />
  <input
    type="range"
    min="320"
    max="1920"
    step="10"
    bind:value="{videoBredde}"
  />
</p>

<p>Høyde: {videoHoyde}</p>
```

---

## GIPHY

Giphy er en nettside med millioner av GIFer (animerte bilder).

Vi kan bruke et API for å hente ned GIFer:

```js
let sokeTekst = "happy dancing kawaii transparent";
	const APInokkel = "N1qjpFZ0Xs79ivyeGB1HpwbhACC*****";

const sporring =
  "https://api.giphy.com/v1/gifs/search?api_key=" +
  APInokkel +
  "&q=" +
  encodeURI(sokeTekst);
const data = await fetch(sporring);
```

**Dette er Ståles personlige API-nøkkel. Jeg får seriøse problemer dersom dere misbruker den.**

---

## Fullstendig GIPHY-funksjon

```js
const APInokkel = "N1qjpFZ0Xs79ivyeGB1HpwbhACC*****";
let gif = "";
let sokeTekst = "";
const hentGif = async () => {
  const offset = Math.ceil(Math.random() * 1);
  const sporring =
    "https://api.giphy.com/v1/gifs/search?api_key=" +
    APInokkel +
    "&q=" +
    encodeURI(sokeTekst) +
    "&limit=1&offset=" +
    offset;
  if (sokeTekst == "") {
    gif = "";
  }
  const respons = await fetch(sporring);
  const resultat = await respons.json();
  gif = await resultat.data[0].images.original.url;
};
```

---

## Vise GIF på skjermen

```html
<img src="{gif}" alt={sokeTekst}>
```

### Vise GIF oppå videoen

```js
// JavaScript
let gifVenstreMarg = videoBredde - 150;
let gifToppMarg = 0;
```

```html
<!-- HTML -->
<img
  src="{gif}"
  style="position: absolute; left: {gifVenstreMarg}px; top: {gifToppMarg}px"
/>
```

---

## Flytte på GIFen

```html
<p>
  x-posisjon: {gifVenstreMarg}<br />
  <input
    type="range"
    min="0"
    max="{videoBredde}"
    step="10"
    bind:value="{gifVenstreMarg}"
  />
</p>
<p>
  y-posisjon: {gifToppMarg}<br />
  <input
    type="range"
    min="0"
    max="{videoHoyde}"
    step="10"
    bind:value="{gifToppMarg}"
  />
</p>
```

---

## Endre størrelse på GIF

```js
// JavaScript
let gifSkalering = 1;
```

```html
<img
  src="{gif}"
  style="position: absolute; left: {gifVenstreMarg}px; 
		 top: {gifToppMarg}px; transform: scale({gifSkalering})"
/>
<input type="range" bind:value="{gifSkalering}" min="0.5" max="5" step="0.1" />
```

---

## localstorage

- `localStorage` er en måte å lagre informasjon i nettleseren.
- Hvert domene har sitt eget `localStorage`, slik du kan lagre ulik informasjon for nrk.no og facebook.com.
- Informasjon i `localStorage` er lagret selv om du åpner nettsiden på nytt, starter datamaskinen på nytt og så videre.
- Siden informasjonen er knyttet til nettleseren så må du bruke samme nettleser for å få tilgang til informasjonen.
	- Informasjonen er altså ikke tilgjengelig hvis du bytter mellom ulike enheter (PC, bærbar PC, mobiltelefon).

**Læreboka sin framgangsmåte for localStorage fungerer ikke!**

---

For å bruke `localStorage` med Sveltekit så gjør vi følgende:

```js
import { browser } from "$app/environment";
if (browser) {
  localStorage.variabelNavn = "verdi";
}
```

- Vi henter inn en komponent kalt `browser`.
	- `browser` er `true` dersom koden kjøres i en nettleser.
	- `browser` er `false` dersom koden kjøres på serveren.
- if-setningen gjør at koden `localStorage.variabelNavn = "verdi"` kun vil kjøres *dersom* i nettleseren.
- Hver gang du skal bruke `localStorage` og du ikke er *sikker* på at koden kun vil kjøres i nettleseren, så bør du sjekke om `browser == true`.
