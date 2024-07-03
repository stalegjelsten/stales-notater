---
{"dg-publish":true,"permalink":"/Orientering/eTiming med spooling av resultater/","title":"eTiming med spooling av resultater","tags":["orientering","etiming"]}
---


# eTiming med spooling av resultater
Spooling av resultater vil si å lese inn resultatene fra MTR4 til [[Orientering/eTiming\|eTiming]] i etterkant av løpet. MTR kan lagre mange tusen brikker. 

## Før løp
- **Nullstill MTR**. Dette er superviktig siden det er vanskelig å velge riktig løp ellers. 
- Still MTR-klokke. MTR-klokka brukes til å synkronisere [[Orientering/Livelox\|Livelox]]. Man får feil starttidspunkter i Livelox dersom denne er feil.
Begge disse punktene gjøres enklest ved å koble MTR til en datamaskin med eTiming. Gå til `Tidtakning → Start kommunikasjon` og deretter synkroniser klokke og nullstill MTR. Se oppsett under [[Orientering/eTiming med spooling av resultater#Spooling\|#Spooling]]

## Spooling av tider

### Under løpet
- Husk å skrive ned brikkenummer til etteranmeldte og løpere som endrer brikke. Ellers blir det ekstra mye jobb for den som skal lage resultatlista å søke seg fram til hvem som eier brikkene.
- Få alle løpere til å lese av brikkene sine under løpet på en [MTR4](https://emit.no/nettbutikk/mini-time-recorder-mtr4/). 
- Koble MTR til PC når du kommer hjem. Hvis du ikke har koblet til MTR til datamaskinen tidligere må du installere [driverne](https://emit.no/en/support-base/emit-mini-time-recorder-mtr4/).

### Før spooling
Før spooling må du passe på at løypene i eTiming er riktige (inkludert målpost). En feil i løypene vil føre til at det blir feil disksjekk på alle løpere. Se [[Orientering/eTiming til sommercup#Import av løyper i eTiming\|eTiming til sommercup#Import av løyper i eTiming]] for mer info.

### Spooling
![](/img/user/_resources/mtr-kommunikasjon.png)
Åpne tidtakervinduet, søk etter riktig port og åpne kommunikasjon med MTR.

**Dersom klokka i MTR er feil så bør du velge `Spool data kun til logfil` og lese om [[Orientering/eTiming med spooling av resultater#Endre tidspunkter i logfila\|hvordan endre tidspunkter i logfila lenger nede]].**

![refresh-ie.jpg](/img/user/_resources/refresh-ie.jpg)
Trykk på ikonet med med grønne piler som går i ring. Dette er symbolet for å spoole tider.

![](/img/user/_resources/spoole-etiming.png)

Trykk `Hent status` for å finne ut hvilke løp og brikker som ligger i minnet på MTR. Det er vanskelig å spoole kun riktig løp, derfor er det lurt å ha slettet alle data i MTR før løpet og lese inn alle tider nå med `Hent alle data`. Hvis du bare vil lese inn noen tider så er trykker du `Hent data fra ett løp`. Skriv deretter inn løpsnummeret. Løpsnummeret er radnummeret slik som jeg har prøvd å skrive inn i bildet over (1, 2, 3, …, 8 i dette tilfellet).

Du kan selv velge om du vil `Spool data kun til logfil`. Jeg pleier å ikke huke av på dette valget, på denne måten går brikketidene direkte inn i eTiming. Hvis du merker av for `Spool data kun til logfil` er du nødt til å lese inn tidene fra logfila ved å trykke på `LOG` knappen i tidtakingsvinduet.

Dersom du spooler alle tider så vil de nyeste tidene med brikkene overskrive gamle tider med brikkene. Dersom du ikke har slettet tidene på MTR fra tidligere vil noen av dagens påmeldte deltakere som ikke har løpt få status DSQ. Dette skjer siden vi leser inn en gammel brikketid på dem.

## Endre tidspunkter i logfila
Hvis klokka i MTR er feil så vil start- og målgangstid til hver løper bli feil når man spooler. Dette gir krøll med [[Orientering/Livelox\|Livelox]]. Det er derfor lurt å fikse på tidspunktene i logfila før man leser den inn i eTiming.

- Velg `Spool data kun til logfil` når du leser inn fra MTR. 
- Finn ut hvor mange sekunder feil klokka på MTR er ved å lese av displayet og sammenligne med ei riktig klokke.
- Gå til [verktøyet for å endre tidspunkter i logfila](https://stalegjelsten.github.io/mtr-date-modifier/)
- Fyll inn infoen og lim inn all teksten fra logfila i tekstvinduet
- Du kan nå laste ned en ny logfil med riktige tidspunkter
- Les inn den nye logfila i eTiming med `LOG`-knappen i tidtakervinduet

## Videre lesning
Det står en god del informasjon om spooling i [dokumentasjonen til eTiming](https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000138212-etiming-dokumentasjon-orientering), under kapittel 4 *Hente data fra MTR*.
