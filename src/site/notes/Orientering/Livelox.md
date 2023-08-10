---
{"dg-publish":true,"permalink":"/Orientering/Livelox/","title":"Livelox","tags":["orientering"]}
---


# Livelox
[Livelox](https://livelox.com) er en tjeneste som gjør det mulig å sammenligne GPS-sporene til ulike løpere på o-løp.

Dette dokumentet tar for seg administrasjon av arrangementer i Livelox. Livelox har en [engelsk bruksanvisning for arrangører](https://www.livelox.com/Documentation/EventOrganisers) som kan være til hjelp.

## Opprette nytt arrangement i Livelox
Så lenge løpet finnes i Eventor er det lurt å opprette Liveloxarrangementet fra Eventor. Dette har følgende fordeler:
1. Resultatene synkroniseres direkte til Livelox slik at strekktider blir helt nøyaktige
2. Hvis deltakerne har med oppvarming og nedjogg i økta si, så blir dette automatisk kuttet bort

For å opprette arrangementet fra Eventor går du til arrangementet i Eventor `Rediger → Livelox → Importer arrangementet`. Logg inn med din Eventor-konto.

De foreslåtte innstillingene bør passe fint, men det kan være at du ønsker å publisere Livelox litt tidligere enn hva som er foreslått.

>[!info]- Opprette nytt arrangement manuelt i Livelox
>Hvis du vil opprette arrangementet direkte i Livelox er du nødt til å gå til [livelox.com](https://www.livelox.com/), og gå til `Administrer → Arrangementer → Legg til et arrangement`

## Last opp kart
![](/img/user/_resources/livelox-adm.png)

Du må laste opp kartfila til løpet. Jeg anbefaler at du laster opp fila i OCAD-format.
1. Trykk på `Kart` (se skjermbildet)
2. Velg `Last opp et kart direkte til Livelox`. Velg OCAD-fila
3. De aller fleste av KOKs kart er *georeferert*.[^1] Prøv derfor å velge Referansesystem: `UTM / ETRS89 UTM zone 32N (N-E)` og sjekk om det fungerer fint på neste side
4. Velg `En del av kartet` og tegn en passende mangekant på kartet som tar med alle veivalg.
5. Trykk Neste
![](/img/user/_resources/livelox-last-opp-kart.png)

Hvis det viser seg at georefereringen ikke stemmer, så går du tilbake og lar feltet for `Referansesystem` stå tomt. Du må da bruke tre punkter på kartet og tre punkter på satelittbildet til å georeferere. Det er lurt å velge hjørner av bygninger, veikryss, småøyer eller andre detaljer som er enkle å få øye på til dette.

Målestokken på kartet er målestokken til kartfila. Den er nesten alltid satt automatisk riktig. Hvis du velger å printe kartene i større målestokk så skal denne likevel *ikke* endres.

Husk å velge `Lagre` på bunnen av siden når du er fornøyd med kartet. 

## Løyper og klasser

### Laste opp løyper
Last opp Purple Pen fila ved å trykke på `Løyper` og `Velg filer`. Du må sannsynligvis justere litt på postene for at løypa skal ligge riktig oppå kartfila. Velg to tydelige poster og sett disse på riktig plass – da skal resten av postene også bli riktige.

### Fikse klasser
Gå til `Klasser` og velg hvilken løype hver klasse skal ha.

## Diverse problemer som kan oppstå
- *Ingen (eller veldig få) deltakeres GPS-spor dukker opp*. Prøv å laste opp resultater på nytt. Administrer arrangementet i Livelox og ta bort koblingen til resultatene med `Slett resultatkoblinger`. Gå til `Eventor → Dataoverføringer` og last ned resultatene i XML-format. Last opp denne resultatfila til Livelox under `Importer resultat`.
- *Alle GPS-sporene starter på feil tidspunkt*. Sannsynligvis har MTR brikkeavleseren feil klokkeslett. Det er mulig å fikse ved å prøve metoden som er beskrevet her: [[Orientering/eTiming med spooling av resultater#Endre tidspunkter i logfila\|eTiming med spooling av resultater#Endre tidspunkter i logfila]]. Du kan også forsøke menyvalget `Justere strekktider` i Livelox – jeg har ikke prøvd det selv enda.

[^1]: Et georeferert kart inneholder informasjon om koordinatene/posisjonen til kartet.
