---
{"dg-publish":true,"permalink":"/Kunnskap/Magisk skinnende tekst med CSS/","title":"Magisk skinnende tekst med CSS","tags":["css","it1"]}
---


# Magisk skinnende tekst med CSS

![Demonstrasjon av den magiske skinnende teksten](/img/user/_resources/magic-text.gif)

Dette er en veldig kul effekt hvor vi lager en [[Kunnskap/Fargeforløpninger i CSS\|bakgrunnsfargeforløpning]] som er mye større enn teksten vi ønsker å animere. Animasjonen flytter deretter denne bakgrunnen «gjennom» bokstavene slik at det ser ut som at et lys flytter seg langs bokstavene.

## CSS
```css
:root {
  --purple: rgb(123,31,162);
  --violet: rgb(103,58,183);
  --pink: rgb(244,143,177);
}

@keyframes background-pan {
  from {
    background-position: 0% center;
  } to {
    background-position: -200% center;
  }
}

body {
  background-color: rgb(10,10,10);
  display: grid;
  height: 100vh;
  place-items: center;
  margin: 0px;
  overflow: hidden;
}

h1{
  color: white;
  font-family: "Rubrik", "SF Pro", sans-serif;
  font-weight:600;
  padding: 20px;
  text-align:center;
  font-size: clamp(1vw,3vw,6vw);
}

h1 > .magic {
  animation: background-pan 3s linear infinite;
  background: linear-gradient(
  to right,
  var(--purple),
  var(--violet),
  var(--pink),
  var(--purple)
  );
  background-size:200%;
  -webkit-background-clip: text;
  -webkit-text-fill-color:transparent;
  white-space: nowrap;
}
```

## HTML

```html
<h1>Tester en flytende gradient effekt lignende den i <span class="magic">Obsidian</span></h1>
```
