---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-6-1 Arrays/","title":"IT1-6-1 Arrays","tags":["it1","forelesning"]}
---


# IT1-6-1 Arrays

Plan for dagen
- 08.15–10.15: 6.1 Arrays. Læring og oppgaver.
- 10.15–12.00: Tid til egen disp.
- 12.00–13.30: Prøve med programmeringsoppgaver i Svelte

---

## Array
Et *array* er en datatype med indekserte verdier. Jeg tenker på arrays som lister.

Vi kan opprette et array med 3 verdier på denne måten

```javascript
let arraynavn = [verdi1, verdi2, verdi3]
```

| indeks | verdi |
| ---- | ---- |
| 0 | verdi1 |
| 1 | verdi2 |
| 2 | verdi3 |

* Vi kan hente ut verdien av indeks 2 ved å bruke `arraynavn[2]`
* Lengden til et array kan vi hente fra egenskapen *length*: `arraynavn.length`

---

### Oppgave 6.1

a) Opprett et array med 5 verdier. Verdiene skal ha datatype tekststreng.
b) Vis den første, tredje og siste verdien i arrayet på en nettside.

---

#### Løsningsforslag til 6.1
```html

<script>
	let myArr = ["hei", "på", "deg", "min", "venn"]
</script>
{myArr[0]}, {myarr[2]}, {myArr[4]}
```

---

## Eksempel: Gjøre endringer i array

<iframe width="100%" style="aspect-ratio:16/7;" src="https://svelte.dev/repl/f942dca0cc7449c19367eeb3dacdf9c3?version=4.2.8"></iframe>

---

## Arraymetoder

| Metode | Forklaring |
| ---- | ---- |
| `array.push(verdi)` | Legger til element i slutten av arrayet |
| `array.unshift(verdi)` | Legger til element i starten av arrayet |
| `array.pop()` | Fjerner siste element i arrayet |
| `array.shift()` | Fjerner første element i arrayet |
| `array.splice(indeks, antall)` | Sletter, endrer eller legger til elementer i Arrayet |
| `array.join(skilletegn)` | Gjør om arrayet til en tekststreng og skiller verdiene med `skilletegn` |

* Gjør eksempelet s. 228–229 for å gjøre dere kjent med syntaksene til disse metodene

---

## Each-blokker i Svelte
Svelte har en egen blokk som gjør noe for hver verdi i en liste.
<iframe width="100%" style="aspect-ratio:16/7;" src="https://svelte.dev/repl/bde4c52a7a394a20ab976f39c70102c3?version=4.2.8"></iframe>
