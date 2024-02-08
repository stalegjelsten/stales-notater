---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-6-7 Localstorage og lagring/","title":"IT1-6-7 Localstorage og lagring","tags":["it1","forelesning"]}
---


# IT1-6-7 Localstorage og lagring

---

## Eksempel med localstorage

[Klikk](http://localhost:5173/6-25-modifisert)

---

## Localstorage
* `localStorage` er en måte å lagre informasjon i nettleseren. 
* Informasjon i `localStorage` er lagret selv om du åpner nettsiden på nytt, starter datamaskinen på nytt og så videre. 
* Hvert domene har sitt eget `localStorage`, slik du kan lagre ulik informasjon for nrk.no og facebook.com. 

---

## Localstorage i Javascript
I Javascript kan man få tilgang til `localStorage` på følgende måte

```js
localStorage.variabelnavn = "ny verdi"
```

* Hvis `variabelnavn` ikke finnes i `localStorage` så opprettes den.
* Hvis `variabelnavn` allerede finnes i `localStorage` så blir verdien overskrevet.
* Alle variabler i `localStorage` blir automatisk datatype string. Det betyr at tall må gjøres om til `Number` hvis du skal regne med dem.
* 💻 Gjør oppgave 6.24 s. 270

---

## Localstorage i Svelte
**❗ Boka viser en metode som *ikke* fungerer i Svelte! ❗**

Løsning i Svelte
```js
import { browser } from '$app/environment'
if (browser) {
	localStorage.variabelNavn = "verdi"
}
```

- Vi henter inn en komponent kalt `browser`. `browser` er `true` dersom koden kjøres i en nettleser. 
- Koden `localStorage.variabelNavn = "verdi"` vil kun kjøres i netttleseren.

**❗ Hver gang du skal bruke `localStorage` og du ikke er *sikker* på at koden kun vil kjøres i nettleseren, så bør du sjekke om `browser == true`. ❗**

---

## Oppgave: Lag en oppgaveliste

- Lag en variabel `oppgaveliste` med en tom liste som kan inneholde alle oppgavene
- Lag en variabel `nyOppgave` med en tom tekststreng som skal inneholde ordet vi skriver i tekstfeltet
- Lag et tekstfelt som du kobler til verdien av `nyOppgave`
- Lag en funksjon `leggTilListe` som legger til `nyOppgave` i slutten av `oppgaveListe`
	- I slutten av funksjonen bør du ha linja `oppgaveListe = oppgaveListe;` (ellers skjønner ikke Svelte alltd at oppgavelista er oppdatert)
- Lag en knapp som kaller på funksjonen i forrige punkt
- Lag en uordnet liste som viser alle oppgavene fra `oppgaveListe`

---

## Kode så langt
```html
<script>
	let oppgaveliste = [];
	let nyOppgave = '';
	const leggTilListe = () => {
		oppgaveliste.push(nyOppgave);
		oppgaveliste = oppgaveliste;
	};
</script>

<input type="text" bind:value={nyOppgave} /> <button on:click={leggTilListe}>Legg til</button>

<ul>
	{#each oppgaveliste as husketing}
		<li>{husketing}</li>
	{/each}
</ul>
```

---

## Oppgaveliste fortsetter
- Legg til kode som sjekker om vi kjører koden i nettleseren 🌐
	- Dersom vi befinner oss i nettleseren så skal du sjekke om det finnes noe i `localStorage.oppgaver`. Dette kan du gjøre med: `if (localStorage.hasOwnProperty('oppgaver'))`.
	- Hvis det finnes noe i `localStorage.oppgaver` så skal du gjøre dette om til et array og lagre som `oppgaveliste`
- Endre på funksjonen `leggTilListe` slik at den gjør om lagrer innholdet i `handleliste` som en tekststreng i `localStorage.oppgaver`
- Sjekk om localStorage på nettsiden din fungerer 👏
- Lag en ny funksjon `slettOppgaver` som sletter alle oppgavene
- *Avansert utvidelse*: lag en knapp ved siden av hver oppgave som du kan trykke på for å slette oppgaven

---

## Kode så langt
```js
import { browser } from '$app/environment';
let oppgaveliste = [];
let nyOppgave = '';
if (browser) {
	if (localStorage.hasOwnProperty('oppgaver')) {
		oppgaveliste = localStorage.oppgaver.split(',');
	}
}

const leggTilListe = () => {
	oppgaveliste.push(nyOppgave);
	localStorage.oppgaver = oppgaveliste.join(',');
	oppgaveliste = oppgaveliste;
};
```

---

```html
<script>
	import { browser } from '$app/environment';
	let oppgaveliste = [];
	let nyOppgave = '';
	if (browser) {
		if (localStorage.hasOwnProperty('oppgaver')) {
			oppgaveliste = localStorage.oppgaver.split(',');
		}
	}
	const leggTilListe = () => {
		oppgaveliste.push(nyOppgave);
		localStorage.oppgaver = oppgaveliste.join(',');
		oppgaveliste = oppgaveliste;
	};
	const slettOppgaver = () => {
		oppgaveliste = [];
		localStorage.oppgaver = '';
	};
</script>
<input type="text" bind:value={nyOppgave} /> <button on:click={leggTilListe}>Legg til</button>
<ul>
	{#each oppgaveliste as husketing}
		<li>{husketing}</li>
	{/each}
</ul>
<button on:click={slettOppgaver}>Slett oppgaver!</button><!-- KOMMENTAREN ER KUN FOR Å GJØRE TEKSTBOKSEN BREDERE -->
```

---

## 🐄-klikker

- Gjør oppgave 6.26 s. 271 i læreboka
- For å løse oppgave e, så er du kanskje nødt til å bruke dato-objekter i Javascript.
	- `let dato1 = new Date()` lagrer et datoobjekt i variabelen `dato1`
	- Hvis du lagrer et annet datoobjekt, `let dato2 = new Date`, på et senere tidspunkt, så kan du finne differansen mellom disse i millisekunder med å ta `dato2 - dato1`

<iframe src="http://localhost:5173/6-26" style="width:100%; aspect-ratio:1.7/1;"></iframe>
