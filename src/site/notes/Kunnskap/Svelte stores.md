---
{"dg-publish":true,"permalink":"/Kunnskap/Svelte stores/","title":"Svelte stores","tags":["svelte","it1"]}
---


# Svelte stores
En `store` er data i [[Kunnskap/Svelte\|Svelte]] som kan brukes i flere komponenter eller ulike sider. Stores er i utgangspunktet globale – de er delt mellom alle brukere av nettsiden.

## Bruke verdien av en store
Hvis du har en store som heter `height` så kan du hente fram verdien av `height` med `{$height}`.
