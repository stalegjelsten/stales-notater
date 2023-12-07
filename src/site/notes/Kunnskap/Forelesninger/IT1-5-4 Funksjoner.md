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
| 18–20   | 6         |

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

## Funksjoner

```html
<script>
	let statsminister = 'Jonas Gahr Støre';
	function byttStatsminister() {
		statsminister = 'Erna Solberg';
	}
</script>

<h1>Vår statsminister er {statsminister}</h1>
<button on:click={byttStatsminister}>Hva skjer?</button>
```

---

## Funksjoner
- Funksjoner defineres som oftest i starten av `<script>`
	- `function minFunksjon(parameter1, parameter2) { kode }`
- Funksjoner utføres kun når vi ***kaller*** på dem.
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
	let tall = 2;               // definerer tall
	function leggTilEn(x) {     // funksjonen leggTilEn har tar inn en variabel som den kaller for x
		return x + 1;           // funksjonen gir tilbake x + 1
	}
	let nyttTall = leggTilEn(tall); 
	// definerer et nytt tall som bruker funksjonen på det gamle tallet
</script>
{nyttTall}                      <!-- skriver ut det nye tallet til skjermen -->
```
---

## Måter å gjøre et funksjonskall på
Du har funksjonen:
```javascript
function bytt() {
	statsminister = 'Erna Solberg';
}
```

Du kan kalle på funksjonen for eksempel ved å gjøre følgende:
* I `<script>` kan du bruke `bytt()`
* I et `button`-element kan du legge til `on:click={bytt}` (uten parenteser)
	* Hvis du vil bruke parametere i funksjonskallet må du bruke en anonym funksjon, se s. 203: `on:click={ ()  => { leggTilEn(4) }`
* Veldig mange andre muligheter: når du beveger musepekeren over et element, når en variabel endrer seg, når siden lastes inn og så videre.

---

## Arrowfunksjoner
- Ny måte å skrive funksjoner på som **brukes i læreboka**.
- `const funksjonsNavn = (parameter1, parameter2) => { kode }`

```html
<script>
	let statsminister = 'Jonas Gahr Støre';
	const byttStatsminister = () => {
		statsminister = 'Erna Solberg';
	}
</script>

<h1>Vår statsminister er {statsminister}</h1>
<button on:click={byttStatsminister}>Bytt statsminister!</button>
```

- Bruk gjerne denne syntaksen (skrivemåten), men det er først ved anonyme funksjoner (se s. 203) at den er *bedre* enn tradisjonell syntaks.

---

## Funksjoner, metoder og egenskaper

- Enkelt å blande sammen
- En variabel har både metoder og egenskaper knyttet til seg
	- metoder: punktum etter variabelnavn og parenteser
	- egenskaper: punktum etter variabelnavn. Kun `length` som er aktuell for dere.

```javascript
let myString = "hei du";
console.log(myString);         //console.log() er funksjon
console.log(heidu.length);     //length er en egenskap
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
<input type="range" name="" id="pH-slider" min="0" max="14" bind:value={ph} />
<p>Når pH-en til en løsning er {ph}, 
{#if ph < 7}
er den sur <br>
<span style="font-size:4rem;">😢</span>
{:else if ph > 7}
er den basisk <br>
<span style="font-size:4rem;">😫</span>
{:else}
er den nøytral <br>
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
	const snitt = () => {
		return (a + b) / 2;
	};
</script>
<p>a = <input type="number" name="" id="tall1" /></p>
<p>b = <input type="number" name="" id="tall2" /></p>
<p>Gjennomsnitt: {snitt()}</p>
```

---

### 5.30
```html
<script>
	let src = 'http://placekitten.com/200/300';
	let rotasjon = 90;
	const roter = () => {
		rotasjon += 90;
	};
</script>

<img {src} alt="en katt" style="transform: rotate({rotasjon}deg);" on:click={roter} />

<!-- her er det bedre for Universell utforming å bruke en knapp -->
```
