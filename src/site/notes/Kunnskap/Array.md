---
{"dg-publish":true,"permalink":"/Kunnskap/Array/","title":"Array","tags":["javascript","it1"]}
---

# Array

>[!warning] Dette notatet gjelder kun [[Kunnskap/Javascript\|Javascript]]
>Dette notatet omhandler kun Javascript. Det finnes arrays i andre programmeringsspråk, blant annet finnes det [[Numpy\|Numpy]] arrays i [[Kunnskap/Python\|Python]].

Et array er en samling av indekserte elementer. Jeg tenker på arrays som lister med elementer.

Et array defineres med hakeparenteser og komma mellom hvert element i arrayet.

```js
let arrayNavn = [verdi1, verdi2, verdi3]
```

Elementene i arrayet har følgende indekser:

| indeks | verdi |
| ---- | ---- |
| 0 | verdi1 |
| 1 | verdi2 |
| 2 | verdi3 |

* Vi kan hente ut verdien av indeks 2 ved å bruke `arrayNavn[2]`
* Lengden til et array kan vi hente fra egenskapen *length*: `arrayNavn.length`

## Arraymetoder

| Metode | Forklaring |
| ---- | ---- |
| `array.push(verdi)` | Legger til element i slutten av arrayet |
| `array.unshift(verdi)` | Legger til element i starten av arrayet |
| `array.pop()` | Fjerner siste element i arrayet |
| `array.shift()` | Fjerner første element i arrayet |
| `array.splice(indeks, antall)` | Sletter, endrer eller legger til elementer i Arrayet |
| `array.join(skilletegn)` | Gjør om arrayet til en tekststreng og skiller verdiene med `skilletegn` |

### Eksempler på bruk av array.splice()
`array.splice()` kan brukes både til å slette, endre eller legge til elementer i et array. Her kommer derfor noen eksempler på bruk (hentet fra ChatGPT).

#### Fjern elementer fra et array:
```js
let fruits = ['eple', 'banan', 'appelsin', 'drue'];
fruits.splice(1, 2); // Fjerner 2 elementer fra indeks 1
console.log(fruits); // Output: ['eple', 'drue']
```

#### Legg til elementer med sletting
```js
let colors = ['rød', 'blå', 'grønn'];
colors.splice(1, 1, 'gul', 'oransje'); // Fjerner 1 element fra indeks 1 og legger til to nye
console.log(colors); // Output: ['rød', 'gul', 'oransje', 'grønn']
```

#### Bytt ut elementer
```js
let numbers = [1, 2, 3, 4];
numbers.splice(2, 1, 10, 20); // Erstatter 1 element ved indeks 2 med 10 og legger til 20
console.log(numbers); // Output: [1, 2, 10, 20, 4]
```

#### Hent fjernede elementer
```js
let letters = ['a', 'b', 'c', 'd'];
let removed = letters.splice(1, 2); // Fjerner 2 elementer fra indeks 1 og lagrer dem i 'removed'
console.log(letters); // Output: ['a', 'd']
console.log(removed); // Output: ['b', 'c']
```


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/reaktivitet-i-svelte/#array-metoder-i-svelte" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## Array metoder i Svelte


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


</div></div>
