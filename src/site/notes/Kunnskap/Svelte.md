---
{"dg-publish":true,"permalink":"/Kunnskap/Svelte/","title":"Svelte","tags":["it1","svelte"]}
---


# Svelte
Svelte er et rammeverk for å bygge nettsider med javascript.

For å lage en Svelte nettside trenger du [[Kunnskap/node.js\|node.js]] med `npm` installert på datamaskinen. 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/opprette-nytt-svelteprosjekt/#opprette-nytt-svelteprosjekt" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



# Opprette nytt Svelteprosjekt


For å opprette et nytt prosjekt i [[Kunnskap/Svelte\|Svelte]] kan du følge instruksjonen i videoen under.

<iframe src="https://www.youtube.com/embed/dIFvziknTuk" class="youtube" title="" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

I videoen gjør jeg følgende steg:
1. Oppretter enn ny mappe til prosjektet
2. Åpner mappen i [[Kunnskap/Visual Studio Code\|Visual Studio Code]] med menyvalget `File` → `Open Folder`
3. Åpner en terminal i [[Kunnskap/Visual Studio Code\|Visual Studio Code]] med menyvalget `Terminal` → `New Terminal`
4. Skriver inn kommandoen `npm create svelte@latest .`
	1. `npm` er navnet på programmet vi kjører (<abbr>npm</abbr> er [[Kunnskap/node.js\|node package manager]])
	2. `create` betyr at vi skal opprette et nytt prosjekt
	3. `svelte@latest` betyr at prosjekttypen er Svelte, og at vi skal brukes siste versjon av Svelte
	4. `.` betyr at vi skal opprette prosjektet i vår nåværende mappe
5. Gjør følgende valg ved hjelp av piltastene, mellomromstasten og enter
	1. Enter for å bekrefte at vi oppretter prosjektet i nåværende mappe
	2. Velger `Skeleton project` for å få et blankt prosjekt uten innhold
	3. Velger ingen `Type checking` siden vi ikke bruker dette i [[IT1 MOC\|IT1]]
	4. Velger `ESLint` for å hjelpe oss å finne feil og problemer i koden, samt `Prettier` som formaterer koden vår på en fin måte
6. Skriver inn `npm install` for å installere alle pakkene som `npm` har funnet ut at vi trenger til prosjektet
7. Skriver `npm run dev -- --open` for å starte en [[Kunnskap/Svelte\|Svelte]] [[Kunnskap/Server\|Server]] som kompilerer Sveltekoden vår, lager den ferdige [[Kunnskap/HTML\|HTML]]-, [[Kunnskap/CSS\|CSS]]- og [[Kunnskap/Javascript\|Javascript]]-koden og viser oss nettsiden. Denne serveren må kjøre på datamaskinen din for at du skal kunne se nettsiden.
	1. `run dev` kjører et npm script kalt `dev` som du finner i fila `package.json`. Hvis du leter her så vil du se at `dev` egentlig kjører kommandoen `vite dev`.
	2. `--` disse to bindestrekene gjør at Svelte [[Kunnskap/Server\|serveren]] blir tilgjengelig på nettverket på adressen `localhost:5173`.
	3. `--open` gjør at nettsidene åpnes i nettleseren automatisk


</div></div>


## Lenker i Svelte
Hvis man oppretter en mappe kalt `katt` under `src/routes/` og legger inn en `+page.svelte` inn i den mappa (slik at full sti blir `src/routes/katt/+page.svelte`) så blir den Svelte-fila prosessert og tilgjengelig på URLen `katt`. **Mappenavnet blir altså navnet på [[Kunnskap/URL\|URL]]en**.

## Promises i Svelte

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/lese-json-med-java-script/#svelte" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Svelte

{% raw %}
I Svelte så håndteres promises [på følgende måte](https://svelte.dev/tutorial/await-blocks):
```js
<script>
  const URL = "https://api.chucknorris.io/jokes/random";
  const getActivities = async (URL) => {
    const response = await fetch(URL);
    const results = await response.json();
    return results.value;
    //JSON-objektet inneholder en vits i nøkkelen "value"
  };

  const promise = getActivities(URL);
</script>

{#await promise}
  <p>Laster…</p>
{:then quote}
  <p>
    {quote}
  </p>
{:catch error}
  {error.message}
{/await}
```

I Svelte bruker vi altså følgende algoritme
1. Vi definerer en `async` funksjon
2. Vi bruker `await fetch` til å hente URLen. Vi kan legge til en *header* som parameter i funksjonskallet til `fetch`.
3. Vi bruker `await promise.json()` for å gjøre om innholdet til JSON så fort det er tilgjengelig
4. Vi returnerer verdien vi er interesserte i.
5. Vi tilordner funksjonskallet til `promise`. Hvis det er aktuelt å gjøre flere API-kall så bør denne variabelen være [[Kunnskap/Svelte#Dynamiske variable\|dynamisk]].
6. I Svelte bruker vi en `{#await}`-blokk som avventer promisen.

{% endraw %}

### Lese inn lokal JSON-fil med Svelte
I Sveltekit så får du problemer dersom du forsøker å bruke fetch – bruk heller følgende framgangsmåte for å lese inn en lokal JSON-fil.

1. Legg JSON-fila i `src/lib` eller en undermappe som `src/lib/data`.
2. I Svelte-koden så skriver du `import variabelNavn from '$lib/JSONfilnavn.json'`.
3. `variabelNavn` inneholder nå alle dataene fra JSON-fila.

#### Eksempel på å lese inn lokal JSON-fil

Vi har en JSON-fil kalt `objekter.json` som inneholder et array med objektene. Objektene er navnet på lærere og bilen de kjører.
```json
[
	{
		"navn": "Ståle",
		"bil": "Audi A3"
	},
	{
		"navn": "Lars",
		"bil": "Volvo XC 70"
	}
]
```

I Svelte-fila `+page.svelte` så importerer vi arrayet med objekter til variabelen `laerere`. Deretter kan vi vise alle lærerne og bilene deres med en `{#each}`-blokk.
```html
<script>
	import laerere from '$lib/objekter.json'
</script>

{#each laerere as laerer}
	<p>{laerer.navn} kjører {laerer.bil}.</p>
{/each}
```


</div></div>


## Dynamiske variable
```js
let a = 2
let b = 3
$: c = a + b
```

Her er `c` deklarert som en dynamisk variabel. Dersom vi oppdaterer `a` eller `b` så vil `c`oppdateres automatisk. 

## Scoping i CSS
CSS som skrives i Svelte er *scopet* (begrenset) til den nåværende siden. Hvis man ønsker å endre på `body` eller `html` så er man nødt til å gå til det globale scopet ved `:global(body) {}`.

## HTML scripting / templating
- [[Kunnskap/each blokker i Svelte\|each blokker i Svelte]]

## Alle Sveltenotater
- [[Kunnskap/each blokker i Svelte\|each blokker i Svelte]]
- [[Kunnskap/Sveltekit mappestruktur\|Sveltekit mappestruktur]]
- [[Kunnskap/Svelte stores\|Svelte stores]]
- [[Kunnskap/Svelte\|Svelte]]
- [[Kunnskap/Reaktivitet i Svelte\|Reaktivitet i Svelte]]
- [[Kunnskap/Opprette nytt Svelteprosjekt\|Opprette nytt Svelteprosjekt]]
- [[Kunnskap/Lage en liste med alle sider i et prosjekt i Svelte\|Lage en liste med alle sider i et prosjekt i Svelte]]
- [[Kunnskap/Localstorage i Sveltekit\|Localstorage i Sveltekit]]
- [[Kunnskap/Lese JSON med JavaScript\|Lese JSON med JavaScript]]
- [[Kunnskap/Bakgrunnsbilder i Svelte\|Bakgrunnsbilder i Svelte]]
- [[Kunnskap/Animasjoner i Svelte\|Animasjoner i Svelte]]
- [[Kunnskap/Bytt fargemodus på nettsider\|Bytt fargemodus på nettsider]]
- [[Kunnskap/CSS pseudoklasser\|CSS pseudoklasser]]
- [[Kunnskap/Tillegg til Kode 1\|Tillegg til Kode 1]]
- [[Kunnskap/localStorage\|localStorage]]
- [[Kunnskap/node.js\|node.js]]

{ .block-language-dataview}
