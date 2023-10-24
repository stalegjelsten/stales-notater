---
{"dg-publish":true,"permalink":"/Publisert/IT1 øveprøver HTML og CSS/","title":"IT1 øveprøver HTML og CSS","tags":["html","css"]}
---


# IT1 øveprøver HTML og CSS

### Oppgave 1
**B** er riktig. For at et HTML-dokument skal vises som en nettside, må den åpnes i nettleseren.

### Oppgave 2
**D** er riktig. `<h1>` Velkommen til min nettside! `</h1>` er et HTML-element. [[Kunnskap/HTML\|HTML]]

### Oppgave 3
Rekkefølge **D** er riktig.
```html
<!DOCTYPE html>
<html>
<head>
<title> </title>
</head>
<body>
</body>
</html>
```

### Oppgave 4
På grunn av skriftstørrelsene så er sannsynligvis alternativ **C** riktig. Dette er i hvert fall gyldig HTML-kode.
```html
<!DOCTYPE html>
<html lang="no">
    <head> 
        <meta charset="UTF-8">
        <title> Min hjemmeside </title>
    </head>
    <body>
        <h1> Velkommen til min hjemmeside! </h1>
        <p> Her vil det komme mer innhold! </p>
    </body>
</html>
```

### Oppgave 5
**A** er definitivt ikke en del av nettsiden, da vi ikke ser disse fargene i listeelementene.

## Øveprøve kapittel 3

### Oppgave 1
*Nettstedet skal være mulig å kopiere* er ikke et prinsipp i universell utforming. Alternativ **C** er feil. [[Kunnskap/Universell utforming av nettsider\|Universell utforming av nettsider]]

### Oppgave 2
Dette er en fryktelig dårlig utformet oppgave. Her mener jeg at **C** er mest feil fordi:
- De fleste er enige om at `alt`-tekst betyr alternativ tekst.
- Alt-tekst vises når nettleseren ikke kan laste inn bildet
- Alt-teksten vises når printeren ikke kan finne bildet eller ikke klarer å skrive ut bilder
- Hvis ikke bildet også er en lenke, så vil ikke alt-teksten være noen lenketekst.
[[Kunnskap/Universell utforming av nettsider#Bilder, videoer og lyd skal ha tekst som alternativ\|Universell utforming av nettsider#Bilder, videoer og lyd skal ha tekst som alternativ]]

### Oppgave 3
Igjen – dette er en elendig oppgave. Standard skriftstørrelse er 16px dersom ikke annet er angitt i nettleseren eller i `html`-selektoren i CSS. Når vi setter `font-size:200%;` så vil vi derfor vanligvis øke skriftstørrelsen til 32px. Alternativ **D** er riktig.
[[Kunnskap/Enheter og størrelser i CSS#Tekststørrelse\|Enheter og størrelser i CSS#Tekststørrelse]]

### Oppgave 4
Igjen – dette er en elendig oppgave. Relativ em er bredden av bokstaven `m` ved standard skriftstørrelse, altså den som er angitt i `html`-selektoren. Vanligvis er dette 16px, og derfor er alternativ **B** riktig.
[[Kunnskap/Enheter og størrelser i CSS#rem\|Enheter og størrelser i CSS#rem]]

### Oppgave 5
**B** er feil. Disse størrelsene er kun avhengige av størrelsen på nettleservinduet.
[[Kunnskap/Enheter og størrelser i CSS#vh\|Enheter og størrelser i CSS#vh]]

### Oppgave 6
Jeg tolker oppgaven som at jeg selv kan velge layout på periodesystemet. Jeg velger et horisontalt system med `flexbox` og setter en minimums-bredde slik at periodesystemet går over flere rader dersom vi ser på det i en smal nettleser. Her er det selvsagt svært mange løsninger som vil gi full uttelling. (Og ja, jeg vet at dere ikke har lært `repeat(auto-fill, størrelse)` som jeg brukte her)

<p class="codepen" data-height="300" data-default-tab="css,result" data-slug-hash="XWOJyWR" data-editable="true" data-user="stalegjelsten" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
	<span>See the Pen <a href="https://codepen.io/stalegjelsten/pen/XWOJyWR">
	IT1 øveprøve Flex løsning</a> by stalegjelsten (<a href="https://codepen.io/stalegjelsten">@stalegjelsten</a>)
	on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
