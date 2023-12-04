---
{"dg-publish":true,"permalink":"/Kunnskap/node.js/","title":"node.js","tags":["it1"]}
---


# node.js
For å kunne bruke [[Kunnskap/Svelte\|Svelte]] er du nødt til å ha installert *node.js* på datamaskinen. Node.js gjør det mulig å kjøre javascriptkode uten å bruke nettleseren.

## Installere node.js og npm
Instruksjonene gjelder for Microsoft Windows. Denne framgangsmåten installerer både node.js og <abbr>npm</abbr> (Node Package Manager).

- Åpne en terminal, gjerne `Powershell` og skriv inn kommandoen `winget install openjs.nodejs.lts` for å installere versjonen med <abbr>LTS</abbr> ([langtidsstøtte](https://no.wikipedia.org/wiki/Langtidsstøtte)).
- Godta eventuelle dialogbokser og lisensvilkår. Standardinnstillingene skal være ok.
- Lukk og start `powershell` på nytt.
- Skriv inn `npm -v`. Hvis du får tilbake tre tall atskilt av punktum (jeg får tilbake `9.8.1`) så er alt ok. Disse tallene er versjonsnummeret til <abbr>npm</abbr>.

