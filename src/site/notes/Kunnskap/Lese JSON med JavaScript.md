---
{"dg-publish":true,"permalink":"/Kunnskap/Lese JSON med JavaScript/","title":"Lese JSON med JavaScript","tags":["it1","svelte","javascript"]}
---


# Lese JSON med JavaScript

## Lese inn string i JSON-format
Der man man har en streng i JSON-format kan denne leses med `JSON.parse(teskstStreng)`.

```js
const jsonStreng = '[{"key1": 2, "key2": "hei"} , {"key1"; 3, "key2": "hallo"}]'
console.log(JSON.parse(jsonStreng))
```

## Lese inn JSON-fil med vanilla JavaScript
For å lese inn JSON eller andre filer bør man bruke en `async`-funksjon slik at vi gir nettleseren tid til å lese dataene før vi går videre til neste steg i koden. Vi bruker `fetch` til å hente dataene. Følgende eksempel ville kanskje fungert i vanlig javascript

```js
const URL = "https://www.boredapi.com/api/activity"
async function getActivities(URL) {
	const response = await fetch(URL);
	const results = await response.json();
	return results.activity 
	//JSON-objektet har en nøkkel som heter activity som vi ønske r å lese
}

const results = getActivities(URL).then( activities => {
	activities
})
```

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
2. I Svelte-koden så skriver du `import variabelNavn from '$lib/JSONfilnavn.json`
3. `variabelNavn` inneholder nå alle dataene fra JSON-fila

#### Eksempel på å lese inn lokal JSON-fil

Vi har en JSON-fil kalt `objekter.json` som inneholder lærere og bilen de kjører.
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

I Svelte-fila `+page.svelte` så kan vi vise alle lærerne fra `objekter.json` og bilen.

```html
<script>
import laerere from '$lib/objekter.json'
</script>
{#each laerere as laerer}
<p>{laerer.navn} kjører {laerer.bil}.</p>
{/each}
```
