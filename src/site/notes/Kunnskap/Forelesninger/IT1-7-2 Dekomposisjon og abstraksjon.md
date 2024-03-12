---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-7-2 Dekomposisjon og abstraksjon/","title":"IT1-7-2 Dekomposisjon og abstraksjon","tags":["it1","forelesning"]}
---


# IT1-7-2 Dekomposisjon og abstraksjon

IT1 07.03.2024

- _Dekomponere_ = å dele opp et problem i to eller flere biter
- _Abstraksjon_ (i algoritmisk tenkning) = å finne en måte å sen gruppe objekter eller idéer på, blant alle mulige måter å se disse, som gjør at vi kan løse et problem.

---

## Dekomposisjon

_Dekomponere_ = å dele opp et problem i to eller flere biter
Eksempler på dekomposisjon:

- Hvis du skal regne med flersifrede tall så deler du regnestykket opp i mindre regnestykker og gjentar en prosess for hver bit av regnestykket
- Når du legger puslespill kan du begynne med å finne hjørnene og lage rammen først

---

## Abstraksjon

_Abstraksjon_ (i algoritmisk tenkning) = å finne en måte å sen gruppe objekter eller idéer på, blant alle mulige måter å se disse, som gjør at vi kan løse et problem.

Eksempler på abstraksjon:

- Du forstår hva tallet 3 betyr
- Du klarer å lese en tekst selv om den bruker en skrifttype du ikke er vant til

---

## Abstraksjon i kortspill

![h:300](https://upload.wikimedia.org/wikipedia/commons/d/d5/Jack_playing_cards.jpg)

- Diskuter:
  - Hva slags informasjon trenger du abstrahere fra hvert kort hvis du spiller president?
  - Hva slags informasjon trenger du abstrahere fra hvert kort hvis du spiller poker?

Når vi spiller president så trenger vi kun informasjon om verdien på kortet og om kortet er kløver 3 eller ikke.
Når vi spiller poker trenger vi både informasjon om hvilken sort kortet er, samt informasjon om hvilken verdi kortet har.

---

## Abstraksjon og svarte bokser

Det er ikke mulig å titte inn i en svart boks (black box).

<div style="border: white 3px solid; background:black; width: 40%; aspect-ratio:2/1; color:white; display:flex; align-items:center; justify-content: center;">Svart boks</div>

- Mange funksjoner kan tolkes som svarte bokser
  - Vi vet ikke hvordan funksjonen `Math.sqrt()` virker
  - Men vi bryr oss nødvendigvis ikke heller

---

## Gode abstraksjoner

Du bør prøve å skrive programmet ditt slik at den som leser det ikke skal måtte tolke for mye.

Hvilken av linjene nedenfor er enklest å lese/tolke?

```javascript
let avstandAB = Math.sqrt((b.x - a.x) ^ (2 + (b.y - a.y)) ^ 2);
let avstandAB = distanse(a, b);
```


---

