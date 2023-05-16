---
{"dg-publish":true,"permalink":"/Orientering/eTiming med spooling av resultater/","title":"eTiming med spooling av resultater","tags":["orientering"]}
---


# eTiming med spooling av resultater
Spooling av resultater vil si å lese inn resultatene fra MTR4 til [[Orientering/eTiming\|eTiming]] i etterkant av løpet. MTR kan lagre mange tusen brikker. 

## Før løp
- **Nullstill MTR**. Dette er superviktig siden det er vanskelig å velge riktig løp ellers.
- Still MTR-klokke. MTR-klokka brukes til å synkronisere [[Orientering/Livelox\|Livelox]]. Man får feil starttidspunkter i Livelox dersom denne er feil.

## Spooling av tider

### Under løpet
Få alle løpere til å lese av brikkene sine under løpet på en [MTR4](https://emit.no/nettbutikk/mini-time-recorder-mtr4/). Koble MTR til PC når du kommer hjem. Pass på å installere [driverne](https://emit.no/en/support-base/emit-mini-time-recorder-mtr4/).

### Før spooling
Før spooling må du passe på at løypene er riktige (inkludert målpost). En feil i løypene vil føre til at det blir feil disksjekk på alle løpere.

### Spooling
![mtr-kommunikasjon.png](/img/user/_resources/mtr-kommunikasjon.png)
Åpne tidtakervinduet, søk etter riktig port og åpne kommunikasjon med MTR.

![refresh-ie.jpg](/img/user/_resources/refresh-ie.jpg)
Trykk på ikonet med med grønne piler som går i ring. Dette er symbolet for å spoole tider.

![spoole-etiming.png](/img/user/_resources/spoole-etiming.png)
Trykk `Hent status` for å finne ut hvilke løp og brikker som ligger i minnet på MTR. Det er vanskelig å spoole kun riktig løp, derfor er det lurt å ha slettet alle data i MTR før løpet og lese inn alle tider nå med `Hent alle data`. Hvis du bare vil lese inn noen tider så er trykker du `Hent data fra ett løp`. Skriv deretter inn løpsnummeret. Løpsnummeret er radnummeret slik som jeg har prøvd å skrive inn i bildet over (1, 2, 3, …, 8 i dette tilfellet).

Du kan selv velge om du vil `Spool data kun til logfil`. Jeg pleier å ikke huke av på dette valget, på denne måten går brikketidene direkte inn i eTiming. Hvis du merker av for `Spool data kun til logfil` er du nødt til å lese inn tidene fra logfila ved å trykke på `LOG` knappen i tidtakingsvinduet.

Dersom du spooler alle tider så vil de nyeste tidene med brikkene overskrive gamle tider med brikkene. Dersom du ikke har slettet tidene på MTR fra tidligere vil noen av dagens påmeldte deltakere som ikke har løpt få status DSQ. Dette skjer siden vi leser inn en gammel brikketid på dem.

## Videre lesning
Det står en god del informasjon om spooling i [dokumentasjonen til eTiming](https://eqtiming.freshdesk.com/nb-NO/support/solutions/articles/19000138212-etiming-dokumentasjon-orientering), under kapittel 4 *Hente data fra MTR*.
