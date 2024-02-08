---
{"dg-publish":true,"permalink":"/Kunnskap/Løkker i Javascript/","title":"Løkker i Javascript","tags":["javascript","it1"]}
---


# Løkker i Javascript
Løkker utfører en del av koden flere ganger. Vi har ulike typer løkker Javascript, blant annet `for`-løkker og `while`-løkker.

>[!todo] Dette er et uferdig notat
## For-løkker
For-løkker kjører et bestemt antall ganger. I Javascript gir vi ofte for-løkker 3 parametre:

1. Vi tilordner en variabel (ofte `i`) en startverdi
2. Vi lager en betingelse som må være sann for at løkka skal fortsette å kjøre
3. Vi skriver kode som utføres etter hver iterasjon[^1]

I koden nedenfor starter vi med `let i = 0`, og etter hver omgang så vil vi øke `i` med 1 på grunn av uttrykket `i++`. Løkka skal kjøre så lenge `i < 10`. Denne løkka vil altså kjøre 10 ganger, med `i`-verdier fra 0 til og med 9.

```js
for (let i = 0; i < 10; i++;) {
	const tilfeldigTall = math.random()
	console.log("Tall nr. " + i + ": " + tilfeldigTall)
}
```

### For-løkker på arrays
Man vil ofte være nødt til å bruk ei løkke på et [[Kunnskap/Array\|array]]. Eksempelet nedenfor viser hvordan vi kan finne tall i et array som er større enn 5. 

```js
let tall = [3, 9, 4, 8, 0, 4, 2, 5]
for (let i = 0; i < tall.length; i++;) {
	if (tall[i] > 5) {
		console.log(tall[i] + " er større enn 5")
	}
}
```

### For-løkker på arrays med .forEach
`forEach()` er en metode som kan brukes på et [[Kunnskap/Array\|array]]. Vi gir en funksjon som parameter til `forEach()`, denne funksjonen virker på alle elementene i arrayet. Linje 1 nedenfor definerer arrayet med elementene a, b og c. Linje 2 bruker `forEach()`. Funksjonen vi gir til `forEach()` er en arrow-funksjon hvor vi angir at hvert element skal kalles `element`. Vi skal returnere `console.log(element)` for hvert element.

Navnene `mittArray` og `element` kan erstattes med andre variabelnavn.

```js
const mittArray = ['a', 'b', 'c'];
mittArray.forEach((element) => console.log(element));
```

[^1]: iterasjon: en iterasjon er en omgang i ei løkke