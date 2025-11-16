---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-3-2 Fra skisse til nettside 1/","title":"IT1-3-2 Fra skisse til nettside","tags":["it1","forelesning"]}
---



# IT1-3-2 Fra skisse til nettside
Kapittel 3.2. 2023-09-28

**Vi starter uten PC, men med skrivebok eller ev. ark.**

## Læringsmål
* Tenke før man begynner å kode
* Lage **wireframes** som viser layout
* Dele inn nettsiden med semantiske HTML-elementer
	* *Semantikk*: læren språkets innhold eller meningsinnholdet til ord.

---

## Utvikle nettsted
1. Lag en Wireframe som viser innholdet
2. Lag en skisse av trestruktur og filstruktur
3. Skriv inn i wireframen hvilke HTML-elementer som du vil bruke i hver del av nettsiden
4. Lag kode ut fra skissen
	1. Først HTML-kode
	2. Deretter CSS-kode

---

## Wireframe
En *wireframe* er *enkel* skisse som viser plasseringen av innhold på skjermen. 

![h:500](https://cdn-proxy.slickplan.com/wp-content/uploads/2019/03/hand-drawn-wireframe-1024x683.jpeg)

---

### Prøv selv: Wireframe

- Gå til et sosialt medie du bruker (som har profilsider)
- Tegn en wireframe av profilsiden
- Tegn en ny wireframe, der du redesigner profilsiden

![bg contain right:67%](/img/user/Kunnskap/Forelesninger/imgs/it1-strava.png)

---

## Filstruktur
- Egen mappe til hver nettside
- Bruk `index.html` og egen mappe til bilder.
```
39-flexbox/
├─ bilder/
│  ├─ logo.png
│  ├─ katt1.jpg
├─ index.html
├─ om_oss.html
├─ kontakt.html
├─ (stil.css)
```

![bg right:67% contain](/img/user/Kunnskap/Forelesninger/imgs/it1-filstruktur.png)

---

## Utvikle nettsted
1. Lag en Wireframe som viser innholdet
2. Lag en skisse av trestruktur og filstruktur
3. Skriv inn i wireframen hvilke HTML-elementer som du vil bruke i hver del av nettsiden
4. Lag kode ut fra skissen
	1. Først HTML-kode
	2. Deretter CSS-kode

<!-- 
---

## HTML-elementer til inndeling

| HTML-element             | Forklaring                    |
| ------------------------ | ----------------------------- |
| `<header>…</header>`   | topptekst                     |
| `<main>…</main>`       | hovedinnhold                  |
| `<footer>…</footer>`   | bunntekst                     |
| `<nav>…</nav>`         | navigasjon/meny               |
| `<section>…</section>` | innhold som hører sammen      |
| `<article>…</article>` | selvstendig innhold           |
| `<div>…</div>`         | gruppering av diverse innhold |

-->

---

## Semantiske HTML-elementer til inndeling

| Tag         | Forklaring                                                                                                                           |
| ----------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `<header>`  | tittelen på nettsiden, med logo, banner, overskrift og så videre                                                                     |
| `<footer>`  | bunnteksten til nettsiden, med for eksempel kontaktinformasjon, lenker til sosiale medier, hvem som har designet siden, og så videre |
| `<nav>`     | navigasjon, nettsidens meny                                                                                                          |
| `<main>`    | hovedområdet på nettsiden, innebærer typisk alt innhold unntatt header, nav og footer                                                |
| `<section>` | et definert område av nettsiden med innhold som henger sammen                                                                        |
| `<article>` | en lengre, sammenhengende tekst, som er uavhengig av annet innhold                                                                   |
| `<aside>`   | apropos-innhold, for eksempel faktabokser, illustrasjonsbilder eller lignende                                                        |
| `<div>`     | gruppering av diverse innhold                                                                                                        |

---

## Oppbygning av nettside med semantiske HTML-elementer

```html
<header>
	<nav>
		<ul>
			<li></li>
		</ul>
	</nav>
</header>
<main>
<article></article>
<article></article>
<aside></aside>
</main>
```

* Hvorfor er det lurt å bruke semantiske HTML-elementer? (Stikkord: universell utforming)
* Hvorfor bør du skrive HTML-koden før CSS-koden?

---

## Publisere nettsider

Hvis du vil publisere nettsidene du lager på skolen så trenger du en [server](https://stales-notater.vercel.app/Kunnskap/Server) som kan vise fram nettsiden til besøkende. Du kan velge å kjøpe serverplass, eller bruke gratistjenester. 

Jeg bruker GitHub pages (Microsoft), men dette er en tjeneste som skolen ikke har datalagringsavtale med. Hvis du velger å bruke den så er det ditt eget valg. Du trenger ikke legge ut nettsidene på internett for min del.

[Her er en guide som viser hvordan du kan sette opp GitHub pages](https://stales-notater.vercel.app/Kunnskap/Publisere%20nettsider%20hos%20GitHub%20pages/)

---

## Bruke VS code til å skrive python kode

VS code har mange flere funksjoner enn Mu. 

- *IntelliSense* fullfører koden din for deg
- De ulike delene av koden din blir farget for å gi bedre oversikt
- En mye bedre *debugger* for å finne feil i koden
- Du kan skrive Pythonkode i [Jupyter notebooks](https://jupyter.org/). Dette lar deg skrive tekst, matematikk, HTML-kode og Pythonkode i samme dokument. Det lar deg også dele opp koden i ulike blokker som kan kjøres uavhengig av hverandre.

[Her er en guide hvis du vil bytte](https://stales-notater.vercel.app/Kunnskap/Bruke%20VS%20Code%20til%20python%20programmering/)


<!--
tema: Skisse til nettsted
startkl: 12:00
læringsmål:
Tenke før man begynner å kode
Lage wireframes som viser layout
Semantiske HTML-elementer
tidsplan:
10 Oppstart. Wireframe intro
25 Wireframeoppgave
5 Filstruktur
5 Pause
10 Forel: Semantiske elementer
15 Les tips til UU
5 Publisere nettsider
5 VScode til python
12 Egentid
-->