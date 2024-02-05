---
{"dg-publish":true,"permalink":"/Kunnskap/Localstorage i Sveltekit/","title":"Localstorage i Sveltekit","tags":["svelte","it1","it"]}
---


# Localstorage i Sveltekit
Hvis man bruker [Sveltekit](https://kit.svelte.dev/) til å serve [[Kunnskap/Svelte\|Svelte]]-nettsider så kan man ikke bruke [[Kunnskap/localStorage\|localStorage]] direkte. Sveltekit kompilerer nettsiden før den blir tilgjengelig for brukeren, men det finnes ikke noe localStorage for servere. Derfor får vi feilmeldingen `ReferenceError: localStorage is not defined.`
{ #9deef1}


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
