---
{"dg-publish":true,"permalink":"/Kunnskap/CSS pseudoselektorer/","title":"CSS pseudoselektorer","tags":["it1","css"]}
---


# CSS pseudoselektorer

En pseudoselektor i CSS begynner med to kolon, f.eks. `::before` eller `::after`.

## Eksempel på avansert bruk av ::after
På [denne nettsiden](https://stalegjelsten.github.io/IT1/36-css-pseudoselektorer/pseudoselektor-sitatblokk.html) tester jeg pseudoselektoren `::after` i en sitatblokk (`blockqote`).

Jeg har gitt sitatblokken en selvvalg attributt i HTML-koden: `name`. `name` er navnet på personen som har opphavet til sitatet.

```html
<blockquote name="Vestigius">Si vis pacem, para bellum.</blockquote>
```

For å automatisk legge til navnet på opphavspersonen etter sitatet (og få fine anførseltegn rundt sitatet) så brukte jeg følgende CSS-kode.

```css
blockquote::before {
  content: "«";
}
blockquote::after {
  content: "» \a — "attr(name);
  white-space: pre;
  font-style: italic;
}
```

`blockquote::before` gjelder rett før `blockquote` elementet, og vi ber CSS om å sette inn et anførselstegn for å starte sitatet.

I `blockquote::after` så gjør vi noen flere interessante saker.

- `\a` er kode for å legge til et linjeskift i tekst
- `attr(name)` gir beskjed om at vi skal sette inn verdien fra attributten `name` som vi har definert i HTML-koden. Legg merke til at dette står utenfor hermetegnene.
- `white-space: pre;` gjør at nettleseren kommer til å ta `\a` som en *whitespace character*. Uten å definere denne egenskapen så vil `\a` bare vises teksten `\a` i nettleseren.
- Vi setter også teksten til å være kursiv
