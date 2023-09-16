---
{"dg-publish":true,"permalink":"/Lese JSON med JavaScript/","title":"Lese JSON med JavaScript","tags":["it1","svelte","javascript"]}
---


# Lese JSON med JavaScript

## Vanilla JavaScript
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
I Svelte så håndteres promises [på følgende måte](https://svelte.dev/tutorial/await-blocks):
```js
<script>
  const URL = "https://api.chucknorris.io/jokes/random";
  const getActivities = async (URL) => {
    const response = await fetch(URL);
    const results = await response.json();
    return results.value;
    //JSON-objektet har en nøkkel som heter value som vi ønsker å lese
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
