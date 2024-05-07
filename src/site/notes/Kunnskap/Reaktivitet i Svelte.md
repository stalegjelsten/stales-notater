---
{"dg-publish":true,"permalink":"/Kunnskap/Reaktivitet i Svelte/","title":"Reaktivitet i Svelte","tags":["svelte","it1"]}
---


# Reaktivitet i Svelte

>[!warning] Uferdig
>Denne siden er veldig uferdig.

I [[Kunnskap/Svelte\|Svelte]] så er variabler reaktive. Det betyr at så fort du endrer på en variabel så vil den oppdaterte variabelen kunne brukes i andre deler av koden. 

## Reaktive deklarasjoner
I tillegg finnes det reaktive deklarasjoner. I eksempelet under er `count` en vanlig variabel. 

```svelte
let count = 1
$: doubled = count * 2;
```

Vi kan legge til 1 på `count` med en funksjon som `() => { count += 1}`, men i vanlig JavaScript måtte vi da også ha redeklarert `doubled` for at denne skulle tatt hensyn til den nye verdien av `count`. Siden vi har brukt reaktive deklarasjon `$:` så sjekker Svelte hele tiden om innholdet av noen av variablene på høyre side har endret verdi.

>[!important] Reaktivitet deklarasjoner kjøres til slutt
> Reaktive deklarasjoner vil alltid kjøres etter resten av koden i `<script>`.


## Reaktive uttrykk
Man kan egentlig skrive hva som helst etter `$:`. Koden blir kjørt hver gang en av variablene i linja blir oppdatert.

```js
$: if (count >= 10) { 
	alert('count is dangerously high!'); 
	count = 0; 
}
```

## Array metoder i Svelte
{ #22b6b3}


Hvis et [[Kunnskap/Array\|array]] blir endret med en metode som `pop` eller `push`, så vil ikke disse endringene bli synlige før du tilordner arrayvariabelen på nytt.

```js
const addNumber = () => { 
	numbers.push(numbers.length + 1); 
	numbers = numbers;  // Nødvendig
}
```

Istedenfor å bruke en metode kan man bruke spread syntaksen ⤵

```js
const addNumber = () => { 
	numbers = [...numbers, numbers.length + 1]; 
}
```
