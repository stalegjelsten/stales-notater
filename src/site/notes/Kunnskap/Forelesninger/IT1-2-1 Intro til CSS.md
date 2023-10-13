---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-2-1 Intro til CSS/","title":"IT1-2-1 Intro til CSS","tags":["it1","forelesning"]}
---


# IT1-2-1 Intro til CSS

---

## CSS

- CSS står for Cascading Style Sheets og brukes til å endre utseendet på HTML-elementer.
- Vi kan legge inn CSS-kode på 3 ulike måter
  - Direkte som et attributt i HTML-elementet:
    - `<p style="color: green;">Grønn tekst</p>`
  - I et `style`element i `head`:
    - `<head><style>h1 {color: green;}</style></head>`
  - I et eget CSS-dokument som vi refererer til i `head`:
    - `<head><link rel="stylesheet" href="stil.css"></head>`

---

## Padding

De fleste HTML-elementer vises som en blokk. Nedenfor har jeg lagt til `style="background-color: darkgreen;"` slik at det blir lett å se blokken (alt det grønne)👇

<h3 style="background-color: darkgreen;">Overskrift</h3>

Padding definerer hvor mye ledig plass det skal være mellom kanten av HTML-blokken og innholdet i blokka. I eksempelet under så har jeg satt lagt til en ekstra padding med CSS koden `padding: 2rem;`. Da vil innholdet (teksten) vises med avstanden 1rem til både toppen, bunnen, venstre side og høyre side.

<h3 style="background-color: darkgreen; padding: 2rem">Overskrift</h3>

---

## Margin

- Margin definerer størrelsen på margene rundt et HTML-element.
- Her har jeg lagt til `margin: 0 4rem 0 10rem;`. Da vil hele blokken bli rykket inn med avstanden
  - 0 fra topp
  - 4rem fra høyre
  - 0 fra bunn
  - 10rem fra venstre

<h3 style="background-color: darkgreen; margin: 0 4rem 0 10rem;">Overskrift</h3>

---

## Farger

### Forgrunnsfarge

Man setter fargen på teksten ved CSS-koden `color: white;`. Verdien til fargen kan være et ord ([se lista over ord](https://www.w3schools.com/cssref/css_colors.php)), eller en fargereferanse som [heksadesimale verdier](https://www.w3schools.com/colors/colors_hexadecimal.asp) (`#FF0000` er f.eks rød)

### Bakgrunnsfarge

Man setter bakgrunnsfargen ved CSS-koden `background-color: black`.

---

## Selektorer

Vi skriver som oftest CSS-kode i `head` eller i et eget CSS-dokument. Vi bruker da _selektorer_ for å velge hvilke HTML-elementer vi ønsker å endre utseendet til.

- `body {background-color: black;}` vil gjøre hele nettsiden svart siden den påvirker hele `body`.
- `h1 {background-color: green;}`vil gjøre bakgrunnen på blokkene til alle H1-overskrifter svart. Resten av nettsiden påvirkes ikke.
  Siden H1 er en mer spesifikk selektor enn body (den påvirker færre elementer) så vil H1-overskriftene på en nettside med begge kodelinjene få grønn bakgrunnsfarge, mens resten av nettsiden får svart bakgrunn.

---

## Fonter

Valg av skrifttype eller _font_ påvirker både lesbarheten og utseendet til nettsiden. Vi kan velge mellom to typer fonter på nettsider

1. Lokale fonter. Disse fontene må være installert på brukerens enhet på forhånd for at de skal vises riktig. Trygge fonter: `Arial`, `Verdana`, `Times New Roman`, `Georgia`, `serif`, `sans-serif`.
2. Webfonter. Disse fontene lastes ned fra internett idet brukeren åpner nettsiden første gang. Nettsiden blir litt tregere, men man kan velge mellom mange flere fonter.

---

### Endre font på nettside

For å bruke `Verdana` på overskrifter og `serif` på vanlig tekst kan du gjøre følgende:

```css
body {
  font-family: "serif";
}
h1,
h2,
h3,
h4,
h5,
h6 {
  font-family: "Verdana";
}
```

---

### Bruke webfonter

[fonts.google.com](https://fonts.google.com/) har mange flotte, gratis fonter. Se [videoen](https://www.youtube.com/watch?v=fsPgvJxrpDE) for demonstrasjon av hvordan man bruker dem.
<iframe src="https://www.youtube.com/embed/fsPgvJxrpDE" class="youtube" title="" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
