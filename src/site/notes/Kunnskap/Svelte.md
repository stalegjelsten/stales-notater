---
{"dg-publish":true,"permalink":"/Kunnskap/Svelte/","title":"Svelte","tags":["it1","svelte"]}
---


# Svelte
Svelte er et rammeverk for å bygge nettsider med javascript.

For å lage en Svelte nettside trenger du [[Kunnskap/node.js\|node.js]] med `npm` installert på datamaskinen. Åpne en terminal og kjør følgende kommandoer

```shell
npm create svelte@latest my-app
cd my-app
npm install
npm run dev
```

Hvis man oppretter en mappe kalt `katt` under `src/routes/` og legger inn en `+page.svelte` inn i den mappa (slik at full sti blir `src/routes/katt/+page.svelte`) så blir den Svelte-fila prosessert og tilgjengelig på URLen `katt`.

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

{% endraw %}


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