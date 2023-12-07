---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-5-4 Funksjoner/","title":"IT1-5-4 Funksjoner","tags":["it1","forelesning"]}
---


# IT1-5-4 Funksjoner

IT1 torsdag 2023-12-07. Pensum: 5.6 funksjoner

- Læringsmål:
  - Skrive og kalle på funksjoner
  - Bruke parametre og returverdier i funksjoner

<div style="display: flex; gap: 2rem; padding: 0;"><div>

| Poeng   | Karakter |
| ------- | -------- |
| 0–5     | 1        |
| 5–9     | 2        |
| 9–13    | 3        |
| 13–15,5 | 4        |
| 15,5–18 | 5        |
| 18–20   | 6        |

</div><div>

**Husk å sjekke karakter fra prøven på Visma**. Gi beskjed hvis ikke karakteren stemmer med tabellen under

</div></div>

---

## Plan for dagen

- Gjennomgang av leksa til i dag
- Gjennomgang av funksjoner
- Oppgave 5.29, 5.33, 5.27
- Kl. 13.15: egentest på itslearning

---

### 5.23

```html
<script>
  let walks = false;
  let quacks = false;
</script>

<label for="walk">Går som en and </label>
<input type="checkbox" name="" id="walk" bind:checked="{walks}" />
<br />
<label for="quack">Kvekker </label>
<input type="checkbox" name="quack" id="quack" bind:checked="{quacks}" />

{#if walks && quacks}
<p>Dette er en and.</p>
{/if}
```

---

### 5.24

```html
<script>
  let hoyde = 1.5;
</script>

<label for="hoyde">Høyde: </label>
<input type="number" id="hoyde" bind:value="{hoyde}" />
{#if hoyde > 3}
<p>
  NB! Du kan ikke skrive inn en høydere høyere enn 3 meter; Kontakt Guinness
  rekordbok dersom du er høyere.
</p>
{:else}
<p>Du er {hoyde} m høy!</p>
{/if}
```

---

### 5.26

```html
<script>
  let pin = 1234;
  let saldo = 2000;
  let inntastet_pin;
  let inntastet_saldo;
</script>

<h3>Velkommen til Svelte minibank, Iben!</h3>
<div>
  <label for="pin">Skriv inn pin koden din</label><br />
  <input type="number" name="" id="pin" bind:value="{inntastet_pin}" />
</div>
<div>
  <label for="saldo">Hvor mye vil du ta ut?</label><br /><input
    type="number"
    name=""
    id="saldo"
  />
  kr
</div>

{#if pin === inntastet_pin && inntastet_saldo <= saldo}
<p style="color:green;">
  Transaksjonen er vellykket. Din nye saldo er: {saldo - inntastet_saldo} kr.
  Takk for besøket.
</p>
{/if}
```

---

## Funksjoner

```html
<script>
  let statsminister = "Jonas Gahr Støre";
  function byttStatsminister() {
    statsminister = "Erna Solberg";
  }
</script>

<h1>Vår statsminister er {statsminister}</h1>
<button on:click="{byttStatsminister}">Hva skjer?</button>
```

---

## Funksjoner

- Funksjoner defineres som oftest i starten av `<script>`
  - `function minFunksjon(parameter1, parameter2) { kode }`
- Funksjoner utføres kun når vi **_kaller_** på dem.
  - Dette er supernyttig! Vi kan kalle på funksjonen når vi trykker på en knapp, når vi har lastet inn en sang/bilde, når klokka blir 16:03:02 osv.

```html
<script>
  let tall = 2;
  function leggTilEn(x) {
    return x + 1;
  }
  let nyttTall = leggTilEn(tall);
</script>
{nyttTall}
```

---

```html
<script>
  let tall = 2; // definerer tall
  function leggTilEn(x) {
    // funksjonen leggTilEn har tar inn en variabel som den kaller for x
    return x + 1; // funksjonen gir tilbake x + 1
  }
  let nyttTall = leggTilEn(tall);
  // definerer et nytt tall som bruker funksjonen på det gamle tallet
</script>
{nyttTall}
<!-- skriver ut det nye tallet til skjermen -->
```

---

## Måter å gjøre et funksjonskall på

Du har funksjonen:

```javascript
function bytt() {
  statsminister = "Erna Solberg";
}
```

Du kan kalle på funksjonen for eksempel ved å gjøre følgende:

- I `<script>` kan du bruke `bytt()`
- I et `button`-element kan du legge til `on:click={bytt}` (uten parenteser)
  - Hvis du vil bruke parametere i funksjonskallet må du bruke en anonym funksjon, se s. 203: `on:click={ ()  => { leggTilEn(4) }`
- Veldig mange andre muligheter: når du beveger musepekeren over et element, når en variabel endrer seg, når siden lastes inn og så videre.

---

## Arrowfunksjoner

- Ny måte å skrive funksjoner på som **brukes i læreboka**.
- `const funksjonsNavn = (parameter1, parameter2) => { kode }`

```html
<script>
  let statsminister = "Jonas Gahr Støre";
  const byttStatsminister = () => {
    statsminister = "Erna Solberg";
  };
</script>

<h1>Vår statsminister er {statsminister}</h1>
<button on:click="{byttStatsminister}">Bytt statsminister!</button>
```

- Bruk gjerne denne syntaksen (skrivemåten), men det er først ved anonyme funksjoner (se s. 203) at den er _bedre_ enn tradisjonell syntaks.

---

## Funksjoner, metoder og egenskaper

- Enkelt å blande sammen
- En variabel har både metoder og egenskaper knyttet til seg
  - metoder: punktum etter variabelnavn og parenteser
  - egenskaper: punktum etter variabelnavn. Kun `length` som er aktuell for dere.

```javascript
let myString = "hei du";
console.log(myString); //console.log() er funksjon
console.log(heidu.length); //length er en egenskap
console.log(heidu.split(" ")); //split() er en metode
```

---

## Løsningsforslag

### 5.27

```html
<script>
  let ph = 7;
</script>
<!-- lager en ekstra lang linje slik at all teksten skal få plass på den samme sliden, kanskje dette er langt nok??? -->
<h1>pH-skala</h1>
<input type="range" name="" id="pH-slider" min="0" max="14" bind:value="{ph}" />
<p>
  Når pH-en til en løsning er {ph}, {#if ph < 7} er den sur <br />
  <span style="font-size:4rem;">😢</span>
  {:else if ph > 7} er den basisk <br />
  <span style="font-size:4rem;">😫</span>
  {:else} er den nøytral <br />
  <span style="font-size:4rem;">😐</span>
  {/if}
</p>
```

---

### 5.29

```html
<script>
  let a = 3;
  let b = 8;
  $: snitt = () => {
    return (a + b) / 2;
  };
</script>

<p>a = <input type="number" name="" id="tall1" bind:value="{a}" /></p>
<p>b = <input type="number" name="" id="tall2" bind:value="{b}" /></p>
<p>Gjennomsnitt: {snitt()}</p>
```

Her lar jeg `snitt` være en [[Kunnskap/Reaktivitet i Svelte\|reaktiv]] funksjon, og dermed kalles den på nytt når `a` eller `b` endrer på seg.

---

### 5.29 alternativ løsning

Dette fungerer ikke:

```html
<script>
  let a = 3;
  let b = 8;
  const gjennomsnitt = () => {
    return (a + b) / 2;
  };
</script>

a = <input type="number" bind:value="{a}" /><br />
b = <input type="number" bind:value="{b}" />

<h3>Gjennomsnittet av {a} og {b} er {gjennomsnitt()}</h3>
```

Problemet er at `gjennomsnitt()` kun blir kalt en gang – når siden blir lastet inn. Se neste side for en løsning som fungerer

---

### 5.29 alternativ 2

```html
<script>
  let a = 3;
  let b = 8;
  const gjennomsnitt = (x, y) => {
    return (x + y) / 2;
  };
</script>

a = <input type="number" bind:value="{a}" /><br />
b = <input type="number" bind:value="{b}" />

<h3>Gjennomsnittet av {a} og {b} er {gjennomsnitt(a,b)}</h3>
```

Grunnen til at dette fungerer er at `a` og `b` endrer verdi, og dermed må `gjennomsnitt(a,b)` kalles på nytt med de nye verdiene.

---

### 5.30

```html
<script>
  let src = "http://placekitten.com/200/300";
  let rotasjon = 90;
  const roter = () => {
    rotasjon += 90;
  };
</script>

<img
  {src}
  alt="en katt"
  style="transform: rotate({rotasjon}deg);"
  on:click="{roter}"
/>

<!-- her er det bedre for Universell utforming å bruke en knapp -->
```

---

### 5.33

```html
<script>
  let saturn = "Saturn";
  let jorda = "Jorda";
  let uranus = "Uranus";
  let merkur = "Merkur";
  let mars = "Mars";
  let g_jorda = 9.82;
  let g_mars = 3.71;
  let g_saturn = 10.4;
  let g_uranus = 8.87;
  let g_merkur = 3.7;
  let masse = 75;
  let planet = "";
</script>

<h1>Tyngde på en fremmed planet</h1>

<p>Skriv inn massen din: <input type="number" bind:value="{masse}" /> kg.</p>
<p>Hvilken planet er du på? <input type="text" bind:value="{planet}" /></p>
{#if planet != saturn && planet != merkur && planet != mars && planet != uranus
&& planet != jorda}
<p>Vi kjenner ikke til denne planeten.</p>
{:else if planet == saturn}
<p>På {planet} er tyngden din {(g_saturn * masse).toFixed(1)} N.</p>
{:else if planet == jorda}
<p>På {planet} er tyngden din {(g_jorda * masse).toFixed(1)} N.</p>
{:else if planet == uranus}
<p>På {planet} er tyngden din {(g_uranus * masse).toFixed(1)} N.</p>
{:else if planet == merkur}
<p>På {planet} er tyngden din {(g_merkur * masse).toFixed(1)} N.</p>
{:else if planet == mars}
<p>På {planet} er tyngden din {(g_mars * masse).toFixed(1)} N.</p>
{/if}
<!-- --------------------------------------------------------------------------------------------------------------------------------------------------- -->
```

---

### 5.33 alternativ

```html
<script>
  let planeter = [
    { navn: "Saturn", tyngdeakselerasjon: 10.4 },
    { navn: "Jorda", tyngdeakselerasjon: 9.81 },
    { navn: "Uranus", tyngdeakselerasjon: 8.87 },
    { navn: "Merkur", tyngdeakselerasjon: 3.7 },
    { navn: "Mars", tyngdeakselerasjon: 3.71 },
  ];
  let masse = 75;
  let planet = "";
</script>
<h1>Tyngde på en fremmed planet</h1>
<p>Skriv inn massen din: <input type="number" bind:value="{masse}" /> kg.</p>
<p>Hvilken planet er du på? <input type="text" bind:value="{planet}" /></p>
{#if planeter.find((o) => o.navn === planet)} På {planeter.find((o) => o.navn
=== planet).navn} er tyngden din {planeter.find( (o) => o.navn === planet
).tyngdeakselerasjon * masse} N. {:else} Vi kjenner ikke til denne planeten.
{/if}
<!-- --------------------------------------------------------------------------------------------------------------------------------------------------- -->
```
