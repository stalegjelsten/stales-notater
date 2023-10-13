---
{"dg-publish":true,"permalink":"/Kunnskap/Selektorer i CSS/","title":"Selektorer i CSS","tags":["css","it1"]}
---


# Selektorer i CSS
En selektor velger ut [[Kunnskap/HTML\|HTML]]-elementer slik at vi kan tilordne egenskaper til elementene.

## Eksempler
```css
h1 {
	color: blue;
}

.rundKantlinje {
	border: 5px solid white;
	border-radius: 5px;
}
```

I CSS koden over er `h1` en *typeselektor*. Alle elementer av typen `h1` på nettsiden vil få *egenskapen* `color` satt til *verdien* `blue`.

`.rundKantlinje` er en *punktselektor* (også kalt klasseselektor). *Alle* HTML elementer med attributten `class="rundKantlinje"` vil få egenskapene `border` og `border-radius` slik som spesifisert i CSS-koden.

## Typer selektorer
Vi har mange ulike typer selektorer

| Selektor                 | Forklaring                                                                                               | Eksempel                                                    |
| ------------------------ | -------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------- |
| Typeselektor             | Velger en type HTML element                                                                              | `h1`                                                        |
| [[Kunnskap/CSS pseudoselektorer\|CSS pseudoselektorer]] | Velger elementer rundt HTML elementet                                                                    | `h1::before`                                                |
| [[Kunnskap/CSS pseudoklasser\|CSS pseudoklasser]]    | Velger spesielle elementer, eller når elementer er i visse tilstander                                    | `div:hover` og `a:visited`                                  |
| Punktselektorer          | Velger alle HTML elementer med attributten `class="klassenavn"`                                          | `h1.spesiell` eller `.rundKantline`                         |
| Hashtagselektor          | Velger alle HTML elementer med attributten `id="idNavn"`. Id-navnet kan kun brukes en gang på nettsiden. | `div#container` eller `#search`                             |
| Attributtselektor        | Velger alle HTML elementer som matcher attributten                                                       | `input[type="range"]` eller `a[href="https://example.org"]` |

## Spesifisitet
CSS har et hierarki[^1] av stiler. Typeselektorene `html` og `body` gjelder hele nettsiden (alt som ligger inne i body). Dersom du setter tekstfargen til blå i body med `body {color: blue;}` så vil dette gjelde for all tekst på siden. Men dersom du også setter `p {color: green;}` så vil all tekst som ligger inne i `p`-tagger bli grønt, mens resten av teksten blir blå. Det er fordi `p` er en mer spesifikk selektor enn `body`.

Pseudoklasser, punktselektorer, hashtagselektorer og attributtselektorer har alle høyere spesifisitet enn typeselektorer. 

La oss se på et annet eksempel ↓

```css
h1 { color: green; }
.blueText { color: blue; }
```

```html
<h1>Denne teksten blir grønn</h1>
<h1 class="blueText">Denne teksten blir blå</h1>
```

I eksempelet ovenfor blir den første overskriften grønn. I den andre overskriften så vil begge linjene med CSS gjelde for overskriften: typeselektoren sier at teksten skal bli grønn, mens punktselektoren sier at den skal bli blå. Punktselektoren er mer spesifikk, derfor blir teksten blå.

## Kombinasjon av selektorer

| Selektor | Forklaring               |
| -------------- | ------------------------ |
| `ul li`        | velger alle li inni ul   |
| `ol li`        | velger alle li inni ol   |
| `ul > li`      | velger første li inni ul |
| `h1 + p`       | velger *første* p ETTER h1 |
| `h1 ~ p`       | velger *alle* p ETTER h1   |

[^1]: Hierarki: å rangere noe, over og under hverandre
