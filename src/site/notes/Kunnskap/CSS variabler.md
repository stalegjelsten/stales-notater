---
{"dg-publish":true,"permalink":"/Kunnskap/CSS variabler/","title":"CSS variabler","tags":["css","it1"]}
---


# CSS variabler
[[Kunnskap/CSS\|CSS]] (Cascading Style Sheets) variabler[^1] defineres og brukes på denne måten

```css
:root {
	--text-color: blue;
}

body {
	color: var(--text-color);
}
```

- `:root` [[Kunnskap/CSS pseudoklasser\|pseudoklassen]] velger (*selekterer*) hele HTML dokumentet. Du kunne også brukt `html` selektoren, men den blir overstyrt av `:root` hvis du også har en `:root` selektor
- Variabelnavnet `--text-color` tilordnes verdien `blue`. *Alle CSS variabelnavn må starte med to bindestreker*.
- Vi bruker variabelen ved å skrive `var(variabelnavn)`. 

Den store fordelen med å bruke variabler er at vi kan endre farger på mange elementer samtidig (og vi kan bruke [[Kunnskap/Javascript\|Javascript]] til å endre på variablene og dermed utseendet til hele nettsiden).

[^1]: Egentlig finnes ikke variabler i <abbr>CSS</abbr> – de heter custom properties eller tilpassede egenskaper
