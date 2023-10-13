---
{"dg-publish":true,"permalink":"/Orientering/ttime til enkle orienteringsløp/","title":"ttime til enkle orienteringsløp","tags":["orientering"]}
---


# ttime til enkle orienteringsløp
Full [[Orientering/ttime brukermanual\|ttime brukermanual]]

## MTR oppsett

### Før løpet
- Tøm MTR for brikker hvis det er mulig ved å koble til PC og nullstille den
- Sett tiden vha. PC hvis mulig, ellers kan man sette den manuelt ved å: 
	- Still dato på MTR ved å trykke $\Downarrow$ og skrive inn ny dato på formatet ÅÅMMDD. Avslutt med $\hookleftarrow$ .
	- Still klokke på MTR ved å trykke på "Set clock A" og skrive inn tiden på formatet HHMMSS. Avslutt med $\hookleftarrow$.

## ttime
Jeg anbefaler at du lager en egen mappe med filer til hvert løp du arrangerer.

### Deltakere
Last ned deltakere via `Eventor entry download`. Bruk brukernavn og passord til Eventor. Sjekk påmeldte deltakere ved å åpne databasen med `Ctrl + E`. Sett ikke startede deltakere til avmeldt (Status A) eller DNS ved å skrive `startnummer/brikkenummer,DNS` for hver deltaker i *Manually*-feltet.

Lagre databasen med deltakere. Jeg anbefaler filendelsen `.csv` slik at fila kan endres i f.eks. Excel hvis du trenger det.

### Les av MTR
Les av (*Spool*) MTR ved å trykke på `MTR`-knappen, velg riktig COM-port og hent `Status`. Velg `Spool all` hvis du har husket å nullstille MTR før løpet, ellers kan også `Spool range` og `Smart spool` prøves ut. Dataene fra MTRen lagres i en `logfil`. 

>[!Tip]
>Hvis MTR har hatt feil dato eller tid kan du lime inn linjene fra `logfila` i [Ståles verktøy](https://stalegjelsten.github.io/mtr-date-modifier/) for å endre tidspunkter. Start- og sluttidene for deltakerne bør være riktige for at Livelox skal gi riktige stemplingstidspunkter.

>[!Tip]
> I ttime kan du velge å bare bruke tider i `logfila` fra datoer som du selv velger. Du trenger altså ikke slette avleste brikker som er fra andre datoer hvis du ikke ønsker det.
> Dersom du ønsker å slette avlesninger selv (for å gjøre logfila mindre eller fordi noen brikker har flere avlesninger) så kan manuelt slette dem fra `logfila`. Åpne `logfila` i en tekstbehandler og let etter linjene du ønsker å slette. Brikkenummer står i kolonne 4 og avlesningstidspunkt står i kolonne 6.. Lagre fila.

### Generer resultater
Trykk `Wizard` i ttime.
- Velg først `logfila` som MTR logfil. 
- Velg deretter databasefila som ttime database
- Velg mappe og filnavn for nettsider med resultater (ikke nødvendig)
- Velg mappe og filnavn for nettsider med strekktider (ikke nødvendig)
- Velg mappe og filnavn for XML database IOF 3.0 format (nødvendig) 
- Velg datoområdet for brikkeavlesning. Kun brikker lest av i dette tidsrommet blir med i resultatene.
- Trykk på knappene med klassenavn ved siden av riktig løype. Du ser også at disse løypene blir markert med avhukning.
- Velg mappe og filnavn for ttime konfigurasjonen (dette er all informasjonen som er nødvendig for å gjenskape resultatene senere. Anbefales) 

## Resultatbearbeiding
Sjekk gjerne nettsidene med resultater som er generert av ttime for å avdekke eventuelle feil. I output-vinduet til ttime vil du også ofte få beskjed om brikkenummer som mangler løpere. Gå i så fall inn i databasen (`ctrl + E`) og legg inn riktige brikkenummer på løpere som har løpt med feil brikke. Du kan også melde på nye løpere i databasevinduet.

Output-vinduet gir også beskjed om antallet på ulike statuskoder, hvis du har noen løpere under `Run` så er det enten løpere som ikke er avlest enda, eller de er ikke registrert som DNS eller avmeldt.

Løpere som er disket og som du ønsker å godkjenne manuelt kan du skrive inn i *manually*-feltet med `startnummer/brikkenummer,tid`, f.eks `506629,34:58` for å godkjenne brikkenummer 506629 med tiden 34:58.

Trykk `Run` på nytt (`Ctrl +R`) for å generere nye resultater.

## Resultater til Eventor
Når du er fornøyd med resultatene dine så laster up resultatene til Eventor. Du har to muligheter.
1. Bruk `Eventor result upload` fra `Database` menyen. Bruk eget Eventor brukernavn og passord.
2. Last opp `results.xml` fila til Eventor ved å åpne Eventor og velge rediger arrangement og Dataoverføring i menyen. Last opp resultatfila i riktig boks.
