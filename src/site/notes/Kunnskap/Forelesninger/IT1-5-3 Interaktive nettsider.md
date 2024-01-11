---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-5-3 Interaktive nettsider/","title":"IT1-5-3-Interaktive nettsider","tags":["it1","forelesning"]}
---


# IT1-5-3-Interaktive nettsider

---

## Repetisjon fra i går
* Svelte er et javascript-rammeverk
* I Svelte skriver vi all kode i `+page.svelte`-filer
* Navnet på mappa under `src/routes` vil være det samme som nettadressen

---

## Hva skrives til skjermen? (Math-funksjoner)
```html
<script>
    let tall = Math.random()*5
    let nyttTall = tall.toFixed(2)
</script>

<h1>Velkommen!</h1>
<p>Her kan jeg skrive en blanding av HTML og Javascriptkode.</p>
<p>Jeg bruker krøllparenteser rundt Javascriptkode: <b>{nyttTall}</b></p>
```

* `Math.random()` gir et tall i intervallet $x \in [0, 1\rangle$.
* Metoden `toFixed(2)` gir avrunding med 2 siffer etter komma.

---

## Hva skrives til skjermen? (Strengmanipulering)
```html
<script>
	let ord = 'fiskebolle';
</script>
<p>Eksempel 1: {ord.length}</p>
<p>Eksempel 2: {ord.split('o').join('ø')}</p>
<p>Eksempel 3: {ord.replaceAll('e', 'a')}</p>
<p>Eksempel 4: {ord.toUpperCase()[4]}</p>
```

* `length` er en egenskap og gir antall tegn i tekststrengen
* `split()` er en metode og den splitter strengen ved tegnet `o`
* `join()` er en metode den kombinerer tekststrengene med tegnet `ø`
* `replaceAll('e', 'a')` er en metode som erstatter alle `e` med `a`
* `toUpperCase()` er en metode som gir store bokstaver
* `[4]` henter ut den 5. bokstaven i tekststrengen

---

## Hva skrives til skjermen? (Datatyper)

```html
<script>
	let tall1 = 5;
	let tall2 = 2;
	let tekst = 'CR';
</script>

<p>Eksempel 1: {tall1 + tall2 + tekst}</p>
<p>Eksempel 2: {tekst + tall1 + tall2}</p>
<p>Eksempel 3: {tekst + (tall1 + tall2)}</p>
```

* Javascript gjør operasjoner fra venstre mot høyre. 
* I eksempel 2 så *konkateneres* teksten og tall1. `CR5` blir da en ny tekststreng. Denne tekststrengen konktaneres deretter med `tall2` til at vi får `CR52`
* `+` betyr altså pluss hvis det står mellom to tall, og konkatenering dersom det står mellom tekst og tall.

---

### Prøv å lage denne layouten i HTML

![h:300](/img/user/Kunnskap/Forelesninger/imgs/IT1-5-3-eksempel-interaktiv.excalidraw.png)

<!--
1. Bruk wireframe og lag skjelett
2. Lag HTML-skjelettet først.
3. bruker < label >
4. 
	-->

---

```html
<script>
	let radius = 3
</script>

<h1>Areal av sirkel</h1>
<label for="radiusfelt">radius: </label>
<input type="number" id="radiusfelt" bind:value={radius}>
<p>arealet er {(radius ** 2 * Math.PI).toFixed(2)}</p>
```

- `bind:value={VARIABELNAVN}` lager en binding mellom variabler i javascript og data som vises i input-felter.
- det arealet som vises som tekst oppdaterer seg automatisk når vi endrer på radius, siden arealet er beregnet direkte fra radius.

---

## Dette fungerer ikke. Hvorfor??

```html
<script>
	let radius = 5;
	let areal = radius ** 2 * Math.PI;
</script>

<h1>Areal av sirkel</h1>
<label for="radius ">radius: </label>
<input type="number" id="radius" bind:value={radius} />
<p>arealet er {areal} cm<sup>2</sup></p>

```

* Nettleseren har beregnet `areal` da koden startet første gang, og den tenker ikke over at arealet var avhengig av radiusen
* Svelte har mulighet for *reaktive variable*, disse defineres sånn: `$: areal = radius ** 2 * Math.PI;`
	* Så fort noe på høyre siden av likhetstegnet endrer seg, så endrer også variabelen `areal` seg. 

---
