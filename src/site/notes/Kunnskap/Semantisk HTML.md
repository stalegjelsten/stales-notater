---
{"dg-publish":true,"permalink":"/Kunnskap/Semantisk HTML/","title":"Semantisk HTML","tags":["it1","html"]}
---


# Semantisk HTML
Semantisk HTML er en måte å skrive HTML på hvor strukturen i dokumentet blir ekstra tydelig. Det gjør blant annet at det er enkelt å gi nettstedet [[Kunnskap/Universell utforming av nettsider\|universell utforming]] og det gjør det enkelt å endre på utseendet kun ved hjelp av CSS.

## Hovedprinsipper
For å skrive semantisk HTML bør du
- Bruke den mest spesifikke HTML-tagen til elementet du ønsker å lage. For eksempel bør du bruke `<button>` istedenfor `<div>` for å lage en knapp, selv om du enkelt kan få begge disse blokkelementene til å se like ut.
- Legge til spesielle semantiske tagger som `<nav>` og `<main>` istedenfor `<div>` med ulike klasser. Se tabellen under.

Hvis man bruker semantiske tagger som `<main>` vil det være mye enklere for en som leser kildekoden å forstå hvordan nettsiden er bygget opp. Det er også enklere for skjermlesere, da de enkelt kan gi brukeren valget mellom å til `nav` eller `main` for å navigere eller lese hovedinnholdet.

Tabellen nedenfor viser de vanligste semantiske taggene. Innholdet i tabellen er lisensiert med CC-BY-SA og hentet fra NDLA. Kilde: Dalsaune, K. A. (2022, 14. mars). Semantisk HTML. NDLA. <https://ndla.no/article/32841>

| Tag         | Forklaring                                                                                                                           |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `<header>`  | tittelen på nettsiden, med logo, banner, overskrift og så videre                                                                     |
| `<footer>`  | bunnteksten til nettsiden, med for eksempel kontaktinformasjon, lenker til sosiale medier, hvem som har designet siden, og så videre |
| `<nav>`     | navigasjon, nettsidens meny                                                                                                          |
| `<main>`    | hovedområdet på nettsiden, innebærer typisk alt innhold unntatt header, nav og footer                                                |
| `<section>` | et definert område av nettsiden med innhold som henger sammen                                                                        |
| `<article>` | en lengre, sammenhengende tekst, som er uavhengig av annet innhold                                                                   |
| `<aside>`   | apropos-innhold, for eksempel faktabokser, illustrasjonsbilder eller lignende                                                        |


## Related
[[Kunnskap/Universell utforming av nettsider\|Universell utforming av nettsider]]
