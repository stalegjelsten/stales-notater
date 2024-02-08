---
{"dg-publish":true,"permalink":"/Kunnskap/localStorage/","title":"localStorage","tags":["javascript","it","it1"]}
---


# localStorage
`localStorage` er en måte å lagre informasjon i nettleseren. Hvert domene har sitt eget `localStorage`, slik du kan lagre ulik informasjon for nrk.no og facebook.com. Informasjon i `localStorage` er lagret selv om du åpner nettsiden på nytt, starter datamaskinen på nytt og så videre. 

Siden informasjonen er knyttet til nettleseren så må du bruke samme nettleser for å få tilgang til informasjonen. Informasjonen er altså ikke tilgjengelig hvis du bytter mellom ulike enheter (PC, bærbar PC, mobiltelefon).

## localStorage i javascript
I [[Kunnskap/Javascript\|Javascript]] kan man få tilgang til `localStorage` på følgende måte

```js
localStorage.variabelnavn = "ny verdi"
```

- Hvis `variabelnavn` ikke finnes i `localStorage` så opprettes den.
- Hvis `variabelnavn` allerede finnes i `localStorage` så blir verdien overskrevet.
- Alle variabler i `localStorage` blir automatisk datatype string. Det betyr at tall må gjøres om til `Number` hvis du skal regne med dem.

## Lagre array av objekter i localStorage
Siden alt som lagres i `localStorage` er tekststrenger, så må vi gjøre noen små endringer dersom vi for eksempel ønsker å lagre et [[Kunnskap/Array\|Array]] av objekter. 
- Når vi lagrer informasjon i `localStorage` kan vi bruke `JSON.stringify(objektNavn)` til å gjøre om objekter til tekststrenger
- Når vi henter informasjon fra `localStorage` så kan vi bruke `JSON.parse(localStorage.variabelnavn)`

Her er et eksempel på en huskeliste i [[Kunnskap/Svelte\|Svelte]] med objekter som består av hva man skal huske og en tilhørende tidsfrist.

```html
<script>
let huskeliste = []
let hva = ""
let naar = ""
import { browser } from '$app/environment'
if (browser) {
    if (localStorage.hasOwnProperty('huskeliste')) {
        huskeliste = JSON.parse(localStorage.huskeliste)
    }
}
const leggTilListe = () => {
    huskeliste.push({"hva": hva, "naar": naar})
    localStorage.huskeliste = JSON.stringify(huskeliste)
    huskeliste = huskeliste // Denne er nødvendig for at Svelte skal forstå at "huskeliste" er oppdatert.
}

</script>

<input type="text" bind:value={hva} placeholder="Hva skal du huske?" />
<input type="text" bind:value={naar} placeholder="Tidsfrist" />
<button on:click={leggTilListe}>Legg til</button>

<ul>
    {#each huskeliste as husketing}
        <li>{husketing.naar}: {husketing.hva}</li>
    {/each}
</ul>
```

## localStorage i Sveltekit

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/localstorage-i-sveltekit/#9deef1" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



Hvis man bruker [Sveltekit](https://kit.svelte.dev/) til å serve [[Kunnskap/Svelte\|Svelte]]-nettsider så kan man ikke bruke [[Kunnskap/localStorage\|localStorage]] direkte. Sveltekit kompilerer nettsiden før den blir tilgjengelig for brukeren, men det finnes ikke noe localStorage for servere. Derfor får vi feilmeldingen `ReferenceError: localStorage is not defined.` 

</div></div>



<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/localstorage-i-sveltekit/#losning" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Løsning
For å bruke `localStorage` med Sveltekit så gjør vi følgende:
```js
import { browser } from '$app/environment'
if (browser) {
	localStorage.variabelNavn = "verdi"
}
```

Vi henter inn en komponent kalt `browser`. `browser` er `true` dersom koden kjøres i en nettleser. `browser` er `false` dersom koden kjøres på serveren. Det betyr at koden `localStorage.variabelNavn = "verdi"` kun vil kjøres *dersom* i nettleseren.

Hver gang du skal bruke `localStorage` og du ikke er *sikker* på at koden kun vil kjøres i nettleseren, så bør du sjekke om `browser == true`.


</div></div>

