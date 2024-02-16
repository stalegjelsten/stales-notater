---
{"dg-publish":true,"permalink":"/Kunnskap/Sveltekit mappestruktur/","title":"Sveltekit mappestruktur","tags":["svelte","it1"]}
---


# Sveltekit mappestruktur
Alle [[Kunnskap/Svelte\|Svelte]] nettsider som lages med Sveltekit er nødt til å følge en fast mappestruktur. Her viser jeg hvordan denne mappestrukturen sannsynligvis kommer til å se ut for et skoleprosjekt.

```tree
prosjektmappe/
├ src/
│ ├ lib/
│ │ └ [filer som skal kunne importeres]
│ ├ routes/
│ │ ├ navnPåSide1/
│ │ │ └ +page.svelte
│ │ ├ navnPåSide2/
│ │ │ └ +page.svelte
│ │ ├ navnPåSide3/
│ │ │ └ +page.svelte
│ │ └ +page.svelte
│ ├ app.html
├ static/
│ └ [bilder og annet statisk]
├ node_modules/
├ package.json
├ svelte.config.js
├ tsconfig.json
└ vite.config.js
```

## Routes
Mappen `src/routes` brukes til alle de ulike sidene inne på nettstedet. For å opprette en ny nettside så
- Lager du en ny mappe under `src/routes`. I vårt eksempel kaller vi mappen `kontakt`
- Lag en fil kalt `+page.svelte` i mappen `kontakt`
```tree
prosjektmappe/
├ src/
│ ├ routes/
│ │ ├ kontakt/
│ │ │ └ +page.svelte
```

Den nye siden vises nå på [http://localhost:5173/kontakt](http://localhost:5173/kontakt). Det er altså mappenavnet som ligger under `src/routes` som blir navnet i [[Kunnskap/URL\|URLen]].

## Lib
I mappen `src/lib` legger du saker som du trenger å importere. Dette kan være [[Kunnskap/Javascript\|Javascript]]kode eller [[Kunnskap/Lese JSON med JavaScript#Lese inn lokal JSON-fil med Svelte\|JOSN-filer]].

## Static
I mappen `static` legger du inn bilder og andre elementer som verken skal endres på eller importeres. JSON-filer kan ikke legges i `static`, disse må legges inn i `src`, og da helst under `src/lib`.

## Node modules
Mappen `node_modules` er en stor mappe som tar mye lagringsplass og består av svært mange filer. Inni denne mappen er det mange programfiler som gjør jobben med å bygge nettstedet med Svelte. 

Du kan trygt slette mappen, for du kan få den tilbake ved å kjøre kommandoen `npm install` i hovedmappen (`prosjektnavn` i mitt eksempel).
