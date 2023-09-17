---
{"dg-publish":true,"permalink":"/Kunnskap/Universell utforming av nettsider/","title":"Universell utforming av nettsider","tags":["it1","html"]}
---


# Universell utforming av nettsider

![Video fra Digitaliseringsdirektoratet om universell utforming](https://youtu.be/mZFpcHSDdvk)

Universell utforming er å utforme omgivelsene våre slik at flest mulig kan delta i samfunnet – uavhengig av funksjonsevne.

Nettsteder som er rettet mot allmennheten i Norge og som enten informerer eller tilbyr tjenester må følge retningslinjer for universell utforming. De norske retningslinjene bygger de internasjonale retningslinjene <abbr>WCAG</abbr> 2.0 (Web Content Accessibility Guidelines). [Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/) har laget en veileder for hvordan vi bør utforme nettsteder som ligger her: <https://www.uutilsynet.no/veiledning/nettsteder/711>

## Hovedprinsipper for universell utforming av nettsteder
![Introduksjon til universell utforming av nettsteder](https://www.youtube.com/watch?v=KSLx3yPwGGY)

<abbr>WCAG</abbr> 2.0 gir oss fire prinsipper for universell utforming av nettsteder

1. [[Kunnskap/Universell utforming av nettsider#Mulig å oppfatte\|#Mulig å oppfatte]]. Informasjon og brukergrensesnitt må være presentert på en slik måte at brukerne kan oppfatte det.
2. [[Kunnskap/Universell utforming av nettsider#Mulig å betjene\|#Mulig å betjene]]. Det må være mulig å betjene brukergrensesnittet og navigere seg på nettstedet.
3. **[[Forståelig\|Forståelig]]**. Det må være mulig å forstå informasjon og betjening av brukergrensesnittet.
4. **Robust**. Innholdet må kunne tolkes på en pålitelig måte av både nettlesere og av kompenserende teknologi (som skjermlesere).

### Mulig å oppfatte

#### Bilder, videoer og lyd skal ha tekst som alternativ
Alle brukere skal kunne oppfatte informasjonen på en nettside, selv om de mangler syn eller hørsel. Derfor har <abbr>WCAG</abbr> et krav om at det brukes tekst som alternativ til video, lyd og bilder. For bilder er det enkelt å legge til en god og bekskrivende `alt`-attributt, mens vi må transkribere lyd og legge på undertekster på video. Heldigvis har det kommet gode verktøy på markedet som kan gjøre dette automatisk (og de blir stadig bedre ved hjelp av AI).

#### Tekst skal være lettlest
For at det skal være enkelt å lese teksten så har vi følgende krav:
- Brukeren skal kunne endre skriftstørrelsen til 200 % uten at det går utover funksjonaliteten til nettsiden
- Kontrastforholdet mellom tekst og bakgrunn skal være minst 4,5:1
- Alle innskrivingsfelt (`input`) skal ha ledetekst som beskriver feltet

Hos [a11y](https://color.a11y.com/ContrastPair/) kan du teste kontrastforholdet mellom to fargekoder.

### Mulig å betjene
Alle brukere skal kunne betjene nettsiden. For det første er det viktig at det er mulig å betjene nettsiden både fra datamaskin og fra smarttelefon eller nettbrett.

I tillegg må vi legge til rette for brukere som kun kan navigere med tastatur (og ikke mus) eller med skjermleser. Ofte vil disse bruke <kbd>Tab</kbd> knappen for å navigere mellom ulike elementer på nettsiden.

Det er som oftest lett å navigere på nettsteder som er laget med [[Kunnskap/Semantisk HTML\|Semantisk HTML]]. Du bør derfor bruke semantiske tagger som `<nav>` og `<main>`.

### Forståelig
>[!todo] Skriv dette avsnittet

### Robust
For at innholdet på nettsiden skal fungere for flest mulig bør du i størst mulig grad velge standardelementer i HTML som er støttet av mange nettlesere. 
