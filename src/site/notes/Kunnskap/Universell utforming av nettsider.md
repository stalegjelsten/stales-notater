---
{"dg-publish":true,"permalink":"/Kunnskap/Universell utforming av nettsider/","title":"Universell utforming av nettsider","tags":["it1","html"]}
---


# Universell utforming av nettsider

<iframe src="https://www.youtube.com/embed/mZFpcHSDdvk" class="youtube" title="Video fra Digitaliseringsdirektoratet om universell utforming" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Universell utforming er å utforme omgivelsene våre slik at flest mulig kan delta i samfunnet – uavhengig av funksjonsevne.

Nettsteder som er rettet mot allmennheten i Norge og som enten informerer eller tilbyr tjenester må følge retningslinjer for universell utforming. De norske retningslinjene bygger på de internasjonale retningslinjene <abbr>WCAG</abbr> 2.0 (Web Content Accessibility Guidelines). [Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/) har laget en [veileder for hvordan vi bør utforme nettsteder](https://www.uutilsynet.no/veiledning/nettsteder/711). 

## Hovedprinsipper for universell utforming av nettsteder
<iframe src="https://www.youtube.com/embed/KSLx3yPwGGY" class="youtube" title="Introduksjon til universell utforming av nettsteder" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

<abbr>WCAG</abbr> 2.0 gir oss fire prinsipper for universell utforming av nettsteder

1. [[Kunnskap/Universell utforming av nettsider#Hovedprinsipp 1 Mulig å oppfatte\|#Hovedprinsipp 1 Mulig å oppfatte]]. Informasjon og brukergrensesnitt må være presentert på en slik måte at brukerne kan oppfatte det.
2. [[Kunnskap/Universell utforming av nettsider#Hovedprinsipp 2 Mulig å betjene\|#Hovedprinsipp 2 Mulig å betjene]]. Det må være mulig å betjene brukergrensesnittet og navigere seg på nettstedet.
3. [[Kunnskap/Universell utforming av nettsider#Hovedprinsipp 3 Forståelig\|#Hovedprinsipp 3 Forståelig]]. Det må være mulig å forstå informasjon og betjening av brukergrensesnittet.
4. [[Kunnskap/Universell utforming av nettsider#Hovedprinsipp 4 Robust\|#Hovedprinsipp 4 Robust]]. Innholdet må kunne tolkes på en pålitelig måte av både nettlesere og av kompenserende teknologi (som skjermlesere).

### Hovedprinsipp 1: Mulig å oppfatte
>Informasjon og brukergrensesnittkomponenter må presenteres for brukere på måter som de kan oppfatte.

[Les mer om hovedprinsipp 1: Mulig å oppfatte hos Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/wcag-standarden/1-mulig-oppfatte/714)

#### Bilder, videoer og lyd skal ha tekst som alternativ
Alle brukere skal kunne oppfatte informasjonen på en nettside, selv om de mangler syn eller hørsel. Derfor har <abbr>WCAG</abbr> et krav om at det brukes tekst som alternativ til video, lyd og bilder. For bilder er det enkelt å legge til en god og beskrivende `alt`-attributt, mens vi må transkribere lyd og legge på undertekster på video. Heldigvis har det kommet gode verktøy på markedet som kan gjøre dette automatisk (og de blir stadig bedre ved hjelp av AI).

#### Tekst skal være lettlest
For at det skal være enkelt å lese teksten så har vi følgende krav:
- Brukeren skal kunne endre skriftstørrelsen til 200 % uten at det går utover funksjonaliteten til nettsiden
- Kontrastforholdet mellom tekst og bakgrunn skal være minst 4,5:1
- Alle innskrivingsfelt (`input`) skal ha ledetekst som beskriver feltet

Hos [a11y](https://color.a11y.com/ContrastPair/) kan du teste kontrastforholdet mellom to fargekoder. Dersom du allerede har laget en nettside kan du teste kontrastforholdene der inne ved å åpne Utviklerverktøyene (<kbd>Ctrl</kbd> <kbd>⇧ Shift</kbd> <kbd>I</kbd>) og trykker på *Tilgjengelighet* eller *Accessibility*. Se figuren under for en sjekk av denne nettsiden foretatt 2023-09-17. 

>[!tip] Simulere fargeblindhet
>Med utviklerverktøyene i de fleste nettlesere kan man simulere ulike former for fargesynhemninger (fargeblindhet). I Firefox velger man *Simulate* under *Accessibility*. Der får man valget mellom ulike typer simuleringer av fargeblindhet.

![uu-stales-notater.png](/img/user/_resources/uu-stales-notater.png)

### Hovedprinsipp 2: Mulig å betjene
>Det må være mulig å betjene brukergrensesnittkomponenter og navigeringsfunksjoner.

Alle brukere skal kunne betjene nettsiden. For det første er det viktig at det er mulig å betjene nettsiden både fra datamaskin og fra smarttelefon eller nettbrett.

[Les mer om hovedprinsipp 2: Mulig å betjene hos Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/wcag-standarden/2-mulig-betjene/716)

#### Tastaturnavigasjon

I tillegg må vi legge til rette for brukere som kun kan navigere med tastatur (og ikke mus) eller med skjermleser. Ofte vil disse bruke <kbd>Tab</kbd> knappen for å navigere mellom ulike elementer på nettsiden. Les mer om [tastaturnavigasjon hos uutilsynet](https://www.uutilsynet.no/veiledning/tastaturnavigasjon/37).

Det er som oftest lett å navigere på nettsteder som er laget med [[Kunnskap/Semantisk HTML\|Semantisk HTML]]. Du bør derfor bruke semantiske tagger som `<nav>` og `<main>`.

### Hovedprinsipp 3: Forståelig
>Det må være mulig å forstå informasjon og betjening av brukergrensesnitt. 

Nettsidene må være forutsigbare, ha enkelt språk og god hjelpefunksjonalitet.

[Les mer om hovedprinsipp 3: Forståelig hos Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/wcag-standarden/3-forstaelig/717)

#### Språk
Alle nettsider må ha definert språket som brukes på nettsiden med `<html lang=”no”>` (erstatt `no` med [språkkoden](https://www.loc.gov/standards/iso639-2/php/code_list.php) som gjelder for ditt språk).

### Hovedprinsipp 4: Robust
>Innholdet må være robust nok til at det kan tolkes på en pålitelig måte av brukeragenter, inkludert kompenserende teknologi.

For at innholdet på nettsiden skal fungere for flest mulig bør du i størst mulig grad velge standardelementer i [[Kunnskap/HTML\|HTML]] som er støttet av mange nettlesere. 

I tillegg bør nettsiden selvsagt ikke inneholde kodefeil. Det er mulig å validere HTML-kode hos [w3c](https://validator.w3.org/).

[Les mer om hovedprinsipp 4: Robust hos Tilsynet for universell utforming av IKT](https://www.uutilsynet.no/wcag-standarden/4-robust/718)

## Ressurser
- [Tilsynet for universell utforming av IKTs norske veileder](https://www.uutilsynet.no/veiledning/nettsteder/711)
- [WAI-ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/) er en veileder for hvordan man gi semantikk og mening til selvlagde komponenter.
