---
{"dg-publish":true,"permalink":"/Kunnskap/Trådløs kommunikasjon(1)/","title":"Trådløs kommunikasjon","tags":["naturfag","fysikk"]}
---


# Trådløs kommunikasjon
Trådløs kommunikasjon kan defineres som all deling av informasjon uten bruk av ledninger. Dette kan gjøres på mange måter:
- [[Kunnskap/Lyd\|lydbølger]] (prating)
- lyssignaler som morsekode med lykter, røyksignaler
- [[Kunnskap/Infrarød stråling\|IR-stråling]] slik som du finner i fjernkontrollen til TVer, varmepumper osv.
- elektromagnetisk stråling

I naturfag så kommer vi til å fokusere på trådløs kommunikasjon ved hjelp av radiobølger, altså [[Kunnskap/Elektromagnetisk stråling\|elektromagnetisk stråling]] med lang bølgelengde. Det er denne typen stråling som brukes til mobildekning, trådløst internett (WiFi), Bluetooth, radio og TV.

## Hovedprinsipper for kommunikasjon med radiobølger

### Sender, mottaker og informasjonsbærer
I all type kommunikasjon så trenger vi en sender, en mottaker og en informasjonsbærer. Informasjonen som skal sendes består alltid av elektriske signaler. I våre tilfeller med radiobølger så er:
- Sender: den enheten som lager det elektriske signalet som skal sendes. F.eks. mobiltelefonen eller microbiten.
- Informasjonsbærer: den elektromagnetiske strålingen (radiobølgen)
- Mottaker: den enheten som tar imot det elektriske signalet og tolker det.

### Protokoll
For å kunne kommunisere må både sender og mottaker være enige om en *protokoll*. Protokollen bestemmer hvilken form kommunikasjonen skal ha, f.eks. hvilke tidspunkter skal mottaker lytte etter meldinger, hvor lang hver melding skal være, hvilken form det er på innholdet i meldingene osv. For radiobølger er det også viktig at både sender og mottaker bruker [[Kunnskap/Antenne\|antenner]] som sender og mottar på samme [[Kunnskap/Bølgelengde\|bølgelengde]] (og dermed samme frekvens).

### Analoge og digitale signaler
Signaler i kommunikasjon er elektriske signaler og vi måler signalet i Volt. Et signal kan være analogt eller digitalt. 

#### Analoge signaler
Et analogt signal kan ha alle mulige forskjellige verdier, det kan altså f.eks. være 0 V, 2,7 V eller 53,824V. Vi bruker veldig sjelden analoge signaler nå til dags, vi finner dem f.eks. i gamle LP-plater (vinylplater med musikk), kassetter eller FM-radioer.

>[!example] Eksempel på analogt lydsignal
>
>![analogue-sound.jpg|300](/img/user/_resources/analogue-sound.jpg)
>Langs x-aksen har vi tid, og langs y-aksen er spenningen til signalet. For lydbølger vil det spenningen tilsvare volumet på lyden. 
>
>Legg merke til hvordan spenningen varierer med tiden, i tillegg ser dere at frekvensen til bølgen endrer seg med tiden. De stedene hvor det er tett mellom bølgetoppene er det høy frekvens (lys tone) og de stedene hvor det er langt mellom bølgetoppene er det lav frekvens (dyp tone).
>
>Figurkilde: Marc Scott, hentet fra <https://github.com/MarcScott/GCSE_Computing_Fundamentals,> CC-BY-SA 4.0.

#### Digitale signaler
Digitale signaler kan kun ha to verdier, vi kaller dem gjerne 0 og 1 og vi kan tenke på det som at en bryter enten er avslått eller påskrudd. En [[Kunnskap/microbit\|microbit]] vil bruke spenningene 0 V og 3,3 V for å representere avslått og påslått bryter.

Hvis vi ønsker å sende 1 0 1 1 så kan dette altså se slik ut:
![digital-signal.png|70%](/img/user/_resources/digital-signal.png)
Radiobølger blir utsatt for interferens og støy fra andre radiobølger i lufta. Derfor vil ofte analoge signaler sprake og være vanskelige å høre. Digitale signaler blir også påvirket, men det er mye lettere for en mottaker å tolke om signalet er høyt eller lavt, selv om vi får litt støy i signalet. Se eksempelet under som viser hvordan et litt «skrukkete» digitalt signal kan tolkes slik at man får den opprinnelige meldingen 1 0 1 1.

![digital-signal-noise.png|70%](/img/user/_resources/digital-signal-noise.png)

### Modulasjon
Modulasjon eller modulering er å kode inn signaler i en bærebølge. Vi skal se på to typer modulasjon i naturfag: AM og FM.

#### Amplitudemodulasjon (AM)

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/amplitudemodulasjon/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">





# Amplitudemodulasjon
Amplitudemodulasjon (AM) er en type modulasjon hvor vi slår sammen et signal og en bærebølge. Vi modulerer amplituden til bærebølgen med signalet vårt, slik at høyt signal vi gi høy amplitude. Et lavt signal vil gi lav amplitude.

![](/img/user/_resources/am.png)


</div></div>


#### Frekvensmodulasjon (FM)

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/kunnskap/frekvensmodulasjon/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">





# Frekvensmodulasjon
Frekvensmodulasjon (FM) er en type modulasjon hvor vi slår sammen et signal og en bærebølge. Vi modulerer inn signalet i bærebølgen ved å modulere frekvensen. Ved høyt signal bruker vi høy frekvens, ved lavt signal bruker vi lav frekvens.

![](/img/user/_resources/fm.png)


</div></div>


## Eksempel på sending av radiobølger med microbit
I dette eksempelet kommer jeg til å bruke en [[Kunnskap/microbit\|microbit]] for å forklare – disse kommuniserer med [[Kunnskap/Trådløs kommunikasjon(1)#Digitale signaler\|digitale signaler]]. Vi tenker oss at en microbit skal kommunisere med en annen microbit. 

### Steg 1: Protokoll
Først må begge microbitene være enige om protokollen. De sender og mottar ved hjelp av Bluetooth på 2,4 GHz. I tillegg er de nødt til å avtale en *radiogruppe* og avtale hva slags informasjon som skal sendes, f.eks. bokstaver i en melding, bilder, kommandoer for å kjøre en bil.

### Steg 2: Digitalisering
Microbiten som skal sende må gjøre om informasjonen som skal sendes til binær kode (nuller og enere). For tekst brukes ofte [ASCII](https://en.wikipedia.org/wiki/ASCII), hvor f.eks. 100 0001 betyr "A". Denne binære koden kan også ses på som et signal som er høyt ved 1 og som er lavt ved 0. 

### Steg 3: Modulering
Microbiten skal nå modulere inn signalet fra forrige steg inn i en bærebølge på 2,4 GHz ved hjelp av en type [[Kunnskap/Frekvensmodulasjon\|frekvensmodulasjon]]. 
- For å representere null (lavt signal) så *reduseres* frekvensen til bærebølgen med minst 115 KHz. Hvis bærebølgen er $2{,}4\times 10^{9}$ Hz så vil det lave signalet ha frekvensen $2{,}399885 \times 10^{9}$ Hz eller lavere.
- For å representere én (høyt signal) så *økes* frekvensen til bærebølgen med minst 115 KHz. Hvis bærebølgen er $2{,}4\times 10^{9}$ Hz så vil det lave signalet ha frekvensen $2{,}40015 \times 10^{9}$ Hz eller høyere.

>[!warning] Modulering i Bluetooth protokollen
> Microbit og andre bluetoothenheter bruker (såvidt jeg klarer å finne ut) en litt modifisert versjon av frekvensmodulasjon. Se [Gaussian Frequency-shift keying](https://en.wikipedia.org/wiki/Frequency-shift_keying#Gaussian_frequency-shift_keying) hos Wikipedia.
> Denne teknikken skal bl.a. sørge for at det skapes mindre støy og interferens for andre enheter i 2,4 GHz-området.

### Steg 4: Sending
I antennen (microbit bruker en [[Kunnskap/Antenne#Kvartbølgeantenne\|kvartbølgeantenne]]) så gjøres det elektriske signalet om til elektromagnetisk stråling. Når det elektriske signalet går gjennom antennen oppstår det [[Kunnskap/Elektromagnetisk stråling\|Elektromagnetiske bølger]]. Disse kan bli fanget opp av en annen microbit. 

For å kunne gjøre om elektriske signaler til elektromagnetisk stråling trenger vi en [[Kunnskap/Antenne\|antenne]].

![microbit-radio-kommunikasjon.excalidraw.png](/img/user/_resources/microbit-radio-kommunikasjon.excalidraw.png)

## Related
[[Kunnskap/Amplitudemodulasjon\|Amplitudemodulasjon]]
[[Kunnskap/Frekvensmodulasjon\|Frekvensmodulasjon]]
[[Kunnskap/Antenne\|Antenne]]
