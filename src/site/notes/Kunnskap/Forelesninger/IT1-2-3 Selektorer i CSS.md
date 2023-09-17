---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-2-3 Selektorer i CSS/","title":"IT1-2-3 Selektorer i CSS","tags":["it1","forelesning"]}
---


# IT1-2-3 Selektorer i CSS

## Læringsmål
- Bruke klasser og id til å endre på spesifikke HTML-elementer
- Bruke `a:link`, `a:visited` og `:hover`
- Bruke noen utvalgte pseudoklasser

---

## Hashtag- og punktselektor

For å endre på bestemte HTML-elementer kan vi bruke attributtene `id` eller `class`. `id` kan kun brukes en gang. `class` kan brukes så mange ganger man ønsker.

```html
<style>
	#hovedOverskrift { egenskap: verdi; }
	.spesiellKlasse { egenskap: verdi; } /* endrer på alle elementer med klasse spesiellKlasse */
	h2.spesiellOverskrift { egenskap: verdi; } /* endrer kun på h2-elementer med klasse spesiellOverskrift */
</style>
<body>
	<h1 id="hovedOverskrift">...</h1>
	<p class="spesiellKlasse">...</p>
</body>
```

---

## Kombinasjon av selektorer

| Selektor | Forklaring               |
| -------------- | ------------------------ |
| `ul li`        | velger alle li inni ul   |
| `ol li`        | velger alle li inni ol   |
| `ul > li`      | velger første li inni ul |
| `h1 + p`       | velger første p ETTER h1 |
| `h1 ~ p`       | velger ALLE p ETTER h1   |

---

## Pseudoselektorer

| Pseudoselektor     | Forklaring                                  |
| ------------------ | ------------------------------------------- |
| `::before`         | setter inn innhold før elementet            |
| `::after`          | setter inn innhold etter elementet          |
| `::first-letter`   | den første bokstaven i et avsnitt           |
| `:hover`           | når markøren føres over et element          |
| `a:link`           | en lenke                                    |
| `a:visited`        | en lenke som er besøkt                      |
| `:active`          | fra du klikker på et element til du slipper |
| `:nth-child(odd)`  | velger annethvert element, oddetall         |
| `:nth-child(even)` | velger annethvert element, partall          |
| `:nth-child(-n+3)` | velger de tre første elementene                                            |

---

### Eksempel: anførselstegn rundt blockquote
Vi bruker koden `<blockquote>` rundt lengre sitater i HTML. Vi kan bruke pseudoselektorer til å legge til norske anførselstegn (« og ») før og etter et sitat.
```css
blockquote::before { content: "«"; }
blockquote::after { content: "»"; }
```

```html
<blockquote>Si vis pacem, para bellum.</blockquote>
```

>«Si vis pacem, para bellum.»

*Obs: CSS-filen som bestemmer stilen på denne forelesningssliden gjør at dette sitatet automatisk får flotte anførselstegn (de gule) på hver side.*

---

### Prøv selv: Pseudoselektor

1. Lag en nettside med lenker hvor du prøver å bruke `a:link`, `a:hover`, `a:visited` for å se forskjellen.
2. Prøv koden under og forklar hvordan den fungerer.

```css
h1 {
	transition: all 0.5s ease-in-out;
}
h1:hover {
	font-size: 64px;
}
```

--- 
