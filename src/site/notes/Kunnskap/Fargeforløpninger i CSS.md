---
{"dg-publish":true,"permalink":"/Kunnskap/Fargeforløpninger i CSS/","title":"Fargeforløpninger i CSS","tags":["css","it1"]}
---


# Fargeforløpninger i CSS

<div style="background: linear-gradient(90deg, #a050e8 0%, #00ff88 50%, #ff00ff 100%); height: 8rem;">&nbsp;</div>

En fargeforløpning er en gradvis overgang mellom ulike farger. Boksen ovenfor er en `div` med høyde `8rem` som viser en lineær forløpning fra lilla til turkis og tilbake til lilla. For å lage effekten brukte jeg følgende CSS-kode:

```css
div {
	background: linear-gradient(90deg, #a050e8 0%, #00ff88 50%, #ff00ff 100%);
}
```

Ved å skrive `linear-gradient` får vi en lineær (rettlinjet) forløpning. Inne i parentesen etter `linear-gradient` har jeg lagt inn følgende parametere
- `90deg` for at forløpningen skal gå i en rett linje fra venstre mot høyre
- `#a050e8 0%` definerer at fargen `a050e8` skal ha være på sitt sterkeste helt ved starten av forløpningen
- `#00ff88 50%` definerer at fargen `00ff88` skal ha være på sitt sterkeste ved midten av forløpningen
- `#ff00ff 100%` definerer at fargen `a050e8` skal ha være på sitt sterkeste (igjen) helt på slutten av forløpningen

Det kan se ut som at fargen til høyre på forløpningen går lenger inn mot midten enn fargen fra venstre side av forløpningen. Dette skjer fordi fargen til høyre er sterkere (den ligger nærmere hvit) enn fargen til venstre.

## Tekst med fargeforløpninger

Å farge tekst med en fargeforløpning gir en stilig effekt (men den bør brukes med forsiktighet – nettsiden bør alltid være godt lesbar!)
<h3 style="background-image: linear-gradient(15deg, #a050e8 0%, #00ff88 55%, #a050e8 100%); background-clip: text; -webkit-text-fill-color: transparent;
">Demonstrerer fargeforløpning i tekst</h3>

>[!example] Eksempel på bruk
>```css
>h3 {
>	background-image: linear-gradient(15deg, #a050e8 0%, #00ff88 65%, #a050e8 100%);
>	background-clip: text;
>	-webkit-text-fill-color: transparent;
>}
>```

For å lage tekst med en fargegradient så kan du bruke CSS til å 
- legge til en gradient som et bakgrunnsbildet på HTML elementet
- clippe bakgrunnen til akkurat det området der teksten er
- bruke en transparent farge på skriften for å se bakgrunnen bak

#### Ressurser
- [Sarah Fossheim](https://fossheim.io/writing/posts/css-text-gradient/) har en veldig god tutorial som viser hvordan man bruker gradients
- [cssgradient.io](https://cssgradient.io/swatches/) er et nettsted hvor du kan finne ferdiglagde gradienter og enkelt designe dine egne stiler
