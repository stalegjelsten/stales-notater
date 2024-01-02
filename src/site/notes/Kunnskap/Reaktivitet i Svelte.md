---
{"dg-publish":true,"permalink":"/Kunnskap/Reaktivitet i Svelte/","title":"Reaktivitet i Svelte","tags":["svelte","it1"]}
---


# Reaktivitet i Svelte

>[!warning] Uferdig
>Denne siden er veldig uferdig.

I [[Kunnskap/Svelte\|Svelte]] så er variabler reaktive. Det betyr at så fort du endrer på en variabel så vil den oppdaterte variabelen kunne brukes i andre deler av koden. 

## Reaktive deklarasjoner
I tillegg finnes det reaktive deklarasjoner. I eksempelet under er `count` en vanlig variabel. 

```svelte
let count = 1
$: doubled = count * 2;
```

Vi kan legge til 1 på `count` med en funksjon som `() => { count += 1}`, men i vanlig JavaScript måtte vi da også ha redeklarert `doubled` for at denne skulle tatt hensyn til den nye verdien av `count`. Siden vi har brukt reaktive deklarasjon `$:` så sjekker Svelte hele tiden om innholdet av noen av variablene på høyre side har endret verdi.

> Reaktive deklarasjoner vil alltid kjøres etter resten av koden i `<script>`.

## Reaktive uttrykk

