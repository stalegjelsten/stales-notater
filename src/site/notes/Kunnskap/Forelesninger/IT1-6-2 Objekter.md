---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-6-2 Objekter/","title":"IT1-6-2 Objekter","tags":["it1","forelesning"]}
---


# IT1-6-2 Objekter
2024-01-11

## Læringsmål
- Kunne lagre data som objekter
- Kunne opprette metoder på objekter
- Kunne bruke `{#each}`-blokker til å kjøre gjennom arrays av objekter

## Plan for dagen
- Gjennomgang av prøven i går
- Forelesning om objekter
- Oppgaver
- (For-løkker i javascript)??

---

## Objekter
Et objekt i [[Javascript\|Javascript]] er en samling av egenskaper (også kalt nøkler) og verdier. For eksempel kan objektet `bil` være definert på følgende måte

```javascript
let bil = {
	merke: "Audi",
	modell: "A3 Quattro",
	motorvolum: 2.0,
	eiere: ["Ståle Gjelsten", "Alf Inge Håland"]
}
```

* Her har objektet `bil` nøklene `merke`, `modell`, `motorvolum` og `eiere`.
* Legg merke til at disse nøklenes verdier kan ha ulike datatyper.

---

```javascript
let bil = {
	merke: "Audi",
	modell: "A3 Quattro",
	motorvolum: 2.0,
}
```

* For å hente fram verdien av en egenskapen `motorvolum` kan vi bruke `bil.motorvolum` 
* `bil.motorvolum * 3` gir svaret…?
	* `6` siden `2.0 * 3 = 6`.
	* Det er også mulig å bruke syntaksen `bil["motorvolum"]` for å hente fram motorvolumet.
* Vi kan også endre på verdiene eller legge til nye egenskaper på samme måte. Dersom vi også vil legge til en egenskap med registreringsår så kan vi gjøre: `bil.registreringsaar = 2013`

---

## Metoder
En metode er en funksjon lagret som egenskapen til et objekt.

```javascript
let bil = {
	merke: "Audi",
	modell: "A3 Quattro", 
	slaaSammenMerkeOgModell() {
		return // HVA KAN STÅ HER??
	}
}
```

---

## Metoder
En metode er en funksjon lagret som egenskapen til et objekt.

```javascript
let bil = {
	merke: "Audi",
	modell: "A3 Quattro", 
	slaaSammenMerkeOgModell() {
		return this.merke + " " + this.modell
	}
}
```

* Hvis man kaller metoden med `bil.slaaSammenMerkeOgModell()` så vil `Audi A3 Quattro` bli returnert. 
* Legg merke til at vi ikke bruker kolon etter navnet på metoden, slik som vi må ved egenskapene `merke` og `modell`.

---

## Each-blokker for arrays av objekter
```html
<script>
let boker = [
	{tittel: "Å vanne blomster om kvelden",
	 forfatter: "Valerie Perrin"},
	{tittel: "I tilfelle brann",
	 forfatter: "Frida Andersen"},
	{tittel: "Den lille mannen fra Argentina",
	 forfatter: "Kristian Klausen"}
]
</script>
<ul>
{#each boker as bok}
	<li> <!-- HVA KAN STÅ HER?? --> </li>
{/each}
</ul>
```

---

## Each-blokker for arrays av objekter
```html
<script>
let boker = [
	{tittel: "Å vanne blomster om kvelden",
	 forfatter: "Valerie Perrin"},
	{tittel: "I tilfelle brann",
	 forfatter: "Frida Andersen"},
	{tittel: "Den lille mannen fra Argentina",
	 forfatter: "Kristian Klausen"}
]
</script>
<ul>
{#each boker as bok}
	<li>{bok.tittel} av {bok.forfatter}</li>
{/each}
</ul>
```

---

## Oppgaver
- 6.09
- 6.11

---

## For løkker i javascript

```js
for (let i = 0; i < 10; i++;) {
	const tilfeldigTall = math.random()
	console.log("Tall nr. " + i + ": " + tilfeldigTall)
}
```

I koden ovenfor starter vi med `let i = 0`, og etter hver omgang så vil vi øke `i` med 1 på grunn av uttrykket `i++`. Løkka skal kjøre så lenge `i < 10`. 

- Denne løkka vil altså kjøre 10 ganger, med `i`-verdier fra 0 til og med 9.

---
