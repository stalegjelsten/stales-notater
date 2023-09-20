---
{"dg-publish":true,"permalink":"/Kunnskap/CSS pseudoklasser/","title":"CSS pseudoklasser","tags":["it1","css"]}
---


# CSS pseudoklasser
Pseduoklasser er en type selektor i [[Kunnskap/CSS\|CSS]] som kan velge andre typer elementer enn vanlige HTML-elementer. Hver pseduoklasse starter med et kolon `:`. Pseudoklasser minner veldig om [[Kunnskap/CSS pseudoselektorer\|CSS pseudoselektorer]] som starter med to kolon `::`.

De vanligste pseduoklassene vi skal jobbe med går på statusen til [[Kunnskap/HTML\|HTML]]-elementer

## Vanlige pseudoklasser

### Bruk :hover for å endre på elementer når man holder musen over dem
```css
button:hover {
	transform: scale(1.2);
}
```

I tilfellet over vil alle knapper vokse med 20 % dersom man holder musen over dem. Du kan sette alle mulige CSS egenskaper i hover pseudoklassen. Hvis du vil at overgangen fra vanlig tilstand til hover-tilstand skal gå gradvis så kan du bruke en [[CSS animasjoner#Enkle animasjon på hover\|CSS animasjon]].

### Bruk a:visited på besøkte lenker
Det er nyttig å skille mellom besøkte og ikke-besøkte lenker på nettstedet. Bruk `a:visited` for å gi besøkte lenker en ny farge.

### Bruk `:root` for å velge hele dokumentet
Det er vanlig å bruke `:root` som selektor for hele dokumentet. Det er vanlig å skrive [[Kunnskap/CSS variabler\|CSS variabler]] i `:root`. Du kan også bruke `html` eller `body` til variablene, men eksempler du finner på nettet vil nok bruke `:root`.

### Bruk `:global` i Svelte for endre hele dokumenter
For å få tilgang til det globale *scopet* i [[Kunnskap/Svelte\|Svelte]] og endre for eksempel `body` så bruker du `:global(body)`. [[Kunnskap/CSS\|CSS]] som skrives direkte i svelte selektere elementer i HTML elementer i samme sveltefil (samt [[Kunnskap/CSS pseudoselektorer\|CSS pseudoselektorer]] og [[Kunnskap/CSS pseudoklasser\|CSS pseudoklasser]])

## Oversikt over noen typer pseudoklasser
| Pseudoklasse       | forklaring                                  |
| ------------------ | ------------------------------------------- |
| `:hover`           | når markøren føres over et element          |
| `a:link`           | en lenke                                    |
| `a:visited`        | en lenke som er besøkt                      |
| `:active`          | fra du klikker på et element til du slipper |
| `:nth-child(odd)`  | velger annethvert element, oddetall         |
| `:nth-child(even)` | velger annethvert element, partall          |
| `:nth-child(-n+3)` | velger de tre første elementene             |
