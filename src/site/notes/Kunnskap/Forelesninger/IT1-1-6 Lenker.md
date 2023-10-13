---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-1-6 Lenker/","title":"IT1-1-6 Lenker","tags":["it1","forelesning"]}
---


# IT1-1-6 Lenker

## Repetisjon fra forrige uke
- VS Code kodesnutter (`html:5`, `ul>li*5`)
- Sette inn bilder med `img`-tagen
- Vektorgrafikk og rastergrafikk

---

### Oppgave – lag din egen vektorgrafikk

```html
<svg name="hovedramme-usynlig" width="500" height="500">
  <rect x="0" y="0" width="440" height="100" style="fill: darkred;" />
  <rect x="0" y="100" width="440" height="150" style="fill: darkblue;" />
  <rect x="0" y="250" width="440" height="100" style="fill: darkred;" />
  <circle cx="180" cy="150" r="60" stroke="none" fill="white" />
</svg>
```

- Legg inn koden over i `body` i HTML
- Det blir nesten likt som flagget under. Klarer du å fikse feilene?
- Ta gjerne utgangspunkt i koden over, og lag Bangladesh sitt flagg.

![h:80](https://upload.wikimedia.org/wikipedia/commons/5/56/Flag_of_Laos.svg)

---

## Lenker
- Lenker binder sammen nettsider
- HTML: `<a href="NETTADRESSE(URL)">Tekst som er klikkbar</a>`

---

### Oppgave – lag nettsted med lenker
- Opprett en mappe med fornuftig navn (f.eks. `34-dyr`)
- Lag et nettsted som ligner på eksempelet nederst på s. 21 i læreboka
- Velg 3 dyr selv

Løsningsforslag: [https://github.com/stalegjelsten/35-dyr](https://github.com/stalegjelsten/35-dyr)

---

## Navigasjon på nettsider
- Hvis filer ligger i samme mappe kan vi lenke til dem med:
	- `<a href="FILNAVN.filendelse">Lenketekst</a>`.
- Hvis filene ligger i en undermappe kalt `bilder` må vi bruke
	- `<a href="bilder/FILNAVN.filendelse">Lenketekst</a>`
- Vi kan lenke til sider på internett ved å bruke
	- `<a href="https://nrk.no">Lenke til NRK</a>`

Vi kan gjøre bilder til lenker med:

```html
<a href="https://no.wikipedia.org/wiki/Ulv">
	<img src="ulv.jpg">
</a>
```

Hvis vi klikker på bildet `ulv.jpg` så vil dette nå føre oss til [Wikipediaartikkelen om ulv](https://no.wikipedia.org/wiki/Ulv)

---
