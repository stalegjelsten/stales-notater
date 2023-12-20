---
{"dg-publish":true,"permalink":"/Kunnskap/Opprette nytt Svelteprosjekt/","title":"Opprette nytt Svelteprosjekt","tags":["it1","svelte"]}
---


# Opprette nytt Svelteprosjekt

For å opprette et nytt prosjekt i [[Kunnskap/Svelte\|Svelte]] kan du følge instruksjonen i videoen under.

<iframe src="https://www.youtube.com/embed/dIFvziknTuk" class="youtube" title="" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

I videoen gjør jeg følgende steg:
1. Oppretter enn ny mappe til prosjektet
2. Åpner mappen i [[Kunnskap/Visual Studio Code\|Visual Studio Code]] med menyvalget `File` → `Open Folder`
3. Åpner en terminal i [[Kunnskap/Visual Studio Code\|Visual Studio Code]] med menyvalget `Terminal` → `New Terminal`
4. Skriver inn kommandoen `npm create svelte@latest .`
	1. `npm` er navnet på programmet vi kjører: node package manager
	2. `create` betyr at vi skal opprette et nytt prosjekt
	3. `svelte@latest` betyr at prosjekttypen er Svelte, og at vi skal brukes siste versjon av Svelte
	4. `.` betyr at vi skal opprette prosjektet i vår nåværende mappe
5. Gjør følgende valg ved hjelp av piltastene, mellomromstasten og enter
	1. Enter for å bekrefte at vi oppretter prosjektet i nåværende mappe
	2. Velger `Skeleton project` for å få et blankt prosjekt uten innhold
	3. Velger ingen `Type checking` siden vi ikke bruker dette i [[IT1 MOC\|IT1]]
	4. Velger `ESLint` for å hjelpe oss å finne feil og problemer i koden, samt `Prettier` som formaterer koden vår på en fin måte
6. Skriver inn `npm install` for å installere alle pakkene som `npm` har funnet ut at vi trenger til prosjektet
7. Skriver `npm run dev -- --open` for å starte en [[Kunnskap/Svelte\|Svelte]] [[Kunnskap/Server\|Server]] som kompilerer Sveltekoden vår, lager den ferdige [[Kunnskap/HTML\|HTML]]-, [[Kunnskap/CSS\|CSS]]- og [[Javascript\|Javascript]]-koden og viser oss nettsiden. Denne serveren må kjøre på datamaskinen din for at du skal kunne se nettsiden.
