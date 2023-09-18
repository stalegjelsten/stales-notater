---
{"dg-publish":true,"permalink":"/Kunnskap/node.js/","title":"node.js","tags":["it1"]}
---


# node.js
For å kunne bruke [[Kunnskap/Svelte\|Svelte]] er du nødt til å ha installert *node.js* på datamaskinen. Node.js gjør det mulig å kjøre javascriptkode uten å bruke nettleseren.

## Installere node.js og npm
Instruksjonene gjelder for Microsoft Windows. Denne framgangsmåten installerer både node.js og <abbr>npm</abbr> (Node Package Manager).

- Gå til [https://nodejs.org/en](https://nodejs.org/en) og last ned versjonen merket med <abbr>LTS</abbr> (Long-Term support).
- Åpne installasjonsfila (den har filendelse `.msi`) etter at den er ferdig lastet ned
- Klikk deg gjennom hele installasjonsprosessen. Standardinnstillingene bør være ok.

Etter at installasjonen er ferdig så kan du sjekke om alt er ok ved å:
- Åpne `powershell` fra Start-menyen 
- Skriv inn `npm -v`. Hvis du får tilbake tre tall atskilt av punktum (jeg får tilbake `9.8.1`) så er alt ok. Disse tallene er versjonsnummeret til <abbr>npm</abbr>.