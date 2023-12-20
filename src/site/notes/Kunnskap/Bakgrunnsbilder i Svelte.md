---
{"dg-publish":true,"permalink":"/Kunnskap/Bakgrunnsbilder i Svelte/","title":"Bakgrunnsbilder i Svelte","tags":["svelte","it1","it"]}
---


# Bakgrunnsbilder i Svelte
For at du skal kunne vise et bakgrunnsbilde på en nettside skrevet i [[Kunnskap/Svelte\|Svelte]] er det noen krav som må oppfylles:

1. Du må velge `Skeleton project` når du oppretter Svelte-prosjektet
2. Bakgrunnsbildet ditt må være tilgjengelig på ett av følgende to steder:
	1. Enten på en nettadresse (for eksempel `https://nettside.no/bilde.jpg`)
	2. Eller i `static`-mappa til prosjektet
3. Du må bruke den spesielle [[Kunnskap/Selektorer i CSS\|CSS-selektoren]] `:global(html)` for å kunne endre bakgrunnsbilde for hele nettsiden.
4. Du må starte Svelte [[Kunnskap/Server\|serveren]] selv med `npm run dev -- --open` og **ikke** bruke det innebygde *Preview*-vinduet i [[VS Code\|VS Code]]. 

## Eksempel på framgangsmåte
Opprett et nytt `skeleton project`. 

- Lag en ny mappe som du kaller `bakgrunnsbilde-test`
- Start VS Code og åpne mappen
- Åpne en terminal i VS Code (f.eks. ved å gå til `Terminal` → `New Terminal` i menylinja eller bruke kommandopaletten)
- Skriv inn kommandoene under i terminalen en etter en. Trykk enter etter hver kommando.
- Etter den første kommandoen så får du noen spørsmål. Trykk `Enter` for å bekrefte valg. Hvis den stiller spørsmål som avsluttes med `(y)` så betyr det at du skal skrive bokstaven `y` og trykke `Enter` for å bekrefte. 
- Velg `Skeleton project`, `No` til Type checking og ja til `ESLint` og `Prettier`

```shell
npm create svelte@latest .
npm install
npm run dev -- --open
```

<script async id="asciicast-rJlo2iy0E0wBrjwLhpxRxjTaw" src="https://asciinema.org/a/rJlo2iy0E0wBrjwLhpxRxjTaw.js" data-size="big" data-rows="15" data-loop="1"></script>

Du skal nå ha fått et helt blank Svelteprosjekt som du kan endre akkurat slik du ønsker.

Legg et bakgrunnsbilde i mappen `static`. Hvis bildet har filnavnet `bilde.jpg` så kan du bruke følgende kode i Svelte for å sette det som bakgrunnsbilde.

```html
<style>
	:global(html) {
		background: url('bilde.jpg');
	}
</style>
```

## Forklaring på hvorfor alt dette er nødvendig
Det er mye arbeid for å få noe så enkelt som et bakgrunnsbilde til å fungere. For å forstå hvorfor det er så komplisert så må vi huske at [[Kunnskap/Svelte\|Svelte]] er laget for å lage komplekse (og enklere) apper og nettsteder. Det er meningen at hvert prosjekt/nettside/app skal være sitt eget prosjekt som du skaper med `npm create svelte@latest PROSJEKTNAVN`.

Du vil ikke kunne se bakgrunnsbildet ditt hvis du velger `Demo project` når du oppretter prosjektet. Det er fordi demoprosjektet allerede inneholder [[Kunnskap/CSS\|CSS]]-kode som definerer hvordan bakgrunnen skal se ut (det er en lys blå bakgrunn). Dermed vil koden vår være i konflikt med demoprosjektet.

Alle bilder må legges i `src`-mappa i Svelte, eller i en undermappa av `src`. Det gjør at alle de ulike `+page.svelte`-filene har tilgang på de samme bildene og ressursene. Det er nyttig dersom vi lager større nettsteder eller apper.

CSS-koden som skrives i `<style>`-taggen i Svelte-koden har et smalt *scope* (CSS-koden gjelder kun for en liten del av HTML-koden). Siden de ferdige nettsidene i Svelte kompileres fra kode fra ulike filer så vil CSS-koden i `<style>` kun gjelde for [[Kunnskap/HTML\|HTML]]-elementer som også finnes i Svelte koden. Dersom vi ønsker å endre på HTML-elementer som vi ikke bruker i Svelte (som for eksempel `<html>`), så er vi nødt til å endre til et *globalt scope* med selektoren `:global(html)`.
