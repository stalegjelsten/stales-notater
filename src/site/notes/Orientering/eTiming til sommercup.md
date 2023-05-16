---
{"dg-publish":true,"permalink":"/Orientering/eTiming til sommercup/","title":"eTiming til sommercup","tags":["etiming","orientering"]}
---


# eTiming til sommercup
Dette er ment som en oppskrift på hvordan man kan bruke eTiming til tidtaking under KOKs sommercupløp. Oppskriften vil fungere både ved tidtaking under arrangementet (polling fra MTR) eller [[Orientering/eTiming med spooling av resultater\|spooling]] av resultater i etterkant av arrangementet.

## Om KOKs sommercup
Sommercupen er en rekke enkle o-løp gjennom sommeren. Løpene har status som nærløp og det tilbys vanligvis 4 løyper:

| Løype | Løypenavn | Klasse                      |
|:-----:|:---------:| --------------------------- |
|   1   |  A-lang   | Herrer A-lang, Damer A-lang |
|   2   |  A-kort   | Herrer A-kort, Damer A-kort |
|   3   |     C     | Herrer C, Damer C           |
|   4   |     N     | Nybegynner                  |

Påmeldingskontingenten har vært kr 0 for KOKs løpere og 30 kr for løpere fra andre klubber som betales via Vipps til #89632.

## Klasseoppsett, frister og kontingenter i Eventor
Under `påmeldingsavgifter og frister` i Eventor så velger du `Rediger, avansert visning`. Bruk kun ett kontingentnivå (slett de andre).
- Navn på avgift: Påmeldingskontingent
- Beløp: 30 kr
- Til dato: Sett tidspunkt for påmeldingsfrist på Eventor
- Fra og til alder: La disse stå åpne
- Kontingentrekkefølge: sett denne til 20

![påmeldingskontingenter-sommercup-eventor.png](/img/user/_resources/p%C3%A5meldingskontingenter-sommercup-eventor.png)

## Last inn påmeldte i eTiming og fiks klasser
I [[Orientering/eTiming\|eTiming]] velger du menyvalget `Data → Datautveksling eventor` og hent påmeldinger til løpet. Dette henter ned deltakere, klasser, klubber og informasjon om påmeldingskontingenter.

### Sette innstillinger for klassene
Vi er nødt til å gjøre noen endringer på klassene slik at det blir riktig for Sommercupen:
- Vi ønsker å bruke brikketid og fristart i alle klasser.
- Nybegynner skal ha urangert resultatliste uten tider. 
- Nybegynner bør ha kjønnskode `X` for å unngå at eTiming gir oss feilmeldinger

Du kan sette disse valgene for klassene manuelt, eller du kan gjøre det automatisk ved hjelp av SQL-spørringer.

#### Gjøre endringer på klassene manuelt
For å gjøre det manuelt så velger `Bruk alltid brikketid` og `Fristart` for hver klasse. For klasse Nybegynner så endrer du `Tidtakingstype` til `Ikke vis tid` og kjønnskoden til `X`.

#### Gjøre endringer på klassene med SQL
For å bruke SQL åpner du menyvalget `Diverse → Spørring`. Nedenfor finner du tre spørringer – du er **nødt til å kjøre dem separat**. Kopier den første linjen nedenfor lim inn i SQL-vinduet (ta bort teksten `sql` i vinduet hvis det står der allerede) og trykk på `Kjør spørring` knappen. Gjenta for de neste linjene. 

```sql
update class set sex = 'X', freestart = True, direct = True;
update class set timingtype = 2 where class like 'N-%pen' or class = 'Nybegynner';
```

![/_resources/etiming-sql.png](/img/user/_resources/etiming-sql.png)

Se [[Orientering/eTiming database\|eTiming database]] for mer informasjon om databasens oppbygning og spørringer.

## Løyper og poster i Purple Pen og eTiming
Hovedprinsipp: **Bruk samme løypenummer i innbydelse, Purple Pen og eTiming**

Jeg anbefaler å bruke oppsettet fra starten av dette dokumentet, der løype 1 er den lengste løypa og løype 4 er nybegynnerløypa.

### Klargjøring av løyper i Purple Pen
- Løyperekkefølgen i Purple Pen må være stigende. Altså skal løype 1 (A-lang) ligge lengst til venstre. Endre rekkefølgen med menyvalget `Løyper → Løyperekkefølge`.
- Løypene **må** inneholde løypenummeret i navnet. Du kan gjerne kalle dem `Løype 1`, `Løype 2` osv.
- Hver løype **må** inneholde klasselista. Denne legger du inn under `Løype → Egenskaper` i feltet `Klasseliste / sekundær tittel`. Klasselista skal inneholde *navnet på hver klasse adskilt med komma*. *Det er svært viktig at navnene på klassene skrives på nøyaktig samme måte som i Eventor*, det vil som oftest si `Herrer A-lang` osv.
- Eksporter `.xml` fil med `Fil → Lag IOF XML-fil`. **Velg IOF XML 3.0** som filtype i `Lagre som`-dialogboksen som hopper opp.
- Lagre også Purple Pen fila slik at du kan laste opp til [[Orientering/Livelox\|Livelox]].

### eTiming import
- `Fil → Importer → Poster og løyper` (eller bruk venstremenyen)
- Velg `Behold course ID / course variation`. Da får løypene samme løypekode som rekkefølgen de hadde i Purple Pen (løype 1 får kode 1)
- Velg IOF XML-fila og pass på at filtypen her også er satt til `IOF XML 3.0`.
- Hvis du blir spurt om å slette andre løyper: svar ja.
- Når du blir spurt om målpost så kan du gjerne legge inn denne allerede. Vi pleier å bruke 249-postene som målposter, men du kan bruke hvilken som helst kode.
- Dobbeltsjekk at løypene nå har riktig løypekode sammenlignet med løypenummer i innbydelse.
- Åpne klasse-oversikten og sjekk at hver klasse har fått riktige løypenummer.
- Tildel løyper til alle løpere ved å åpne klasse-oversikten og gå til menyvalget `Klasse → Oppdater løypenr på løpere`

## Last opp startliste
Gå til menyvalget `Data → Datautveksling eventor` og last opp startliste til Eventor. Sjekk på Eventor at den ser korrekt ut.

## Etteranmeldinger på løpet
Legg inn etteranmeldte på løpet ved å åpne løper-oversikten. 
- Trykk på `+`-tegnet i verktøylinja eller <kbd>ctrl</kbd> + <kbd>N</kbd> for legge til ny løper.
- Fyll inn navn, klasse, klubb og brikkenr. 
	- Hvis løperen skal låne brikke så kan du trykke på avkrysningsboksen merket `Brikke`. Da blir løperen merket med blå farge når hen kommer i mål slik at du vet at du skal samle inn leiebrikken igjen.
- Hvis løperen er under 21 år så anbefaler jeg også at du skriver inn fødselsdato (eller i det minste fødselsår) i `Født`-boksen, f.eks. 1.1.2015. Dette gjør at vi får riktig antall barn, ungdommer og voksne i løpsrapporten som skal leveres. 

## Tidtaking
Du kan velge å ha tidtaking under løpet (polling) eller ved å lese inn resultatene fra MTR4 i etterkant av løpet (spooling). Å ha tidtaking under løpet krever at en person har dette som arbeidsoppgave, men det gjør også at det blir mindre etterarbeid og det er mulig å tilby [[Orientering/LiveRes for etiming\|liveresultater]].

### Tidtaking under løpet
Før løpet så starter du tidtakingsmodulen i eTiming og kobler til en MTR4 til avlesning. Nullstill MTR og synkroniser klokka fra PC til MTRen før du begynner å lese av brikker. [Guiden hos Agder o-krets fra 2019](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) har en god forklaring på hvordan du setter opp MTR, åpner tidtakingen og behandler disk/problemer som oppstår gjennom løpet.

Bruk [[Orientering/LiveRes for etiming\|LiveRes]] for å publisere liveresultater. 

### Lese inn resultater i eTiming etter løpet

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/orientering/e-timing-med-spooling-av-resultater/" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">





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


</div></div>


## Resultater
Publiser resultater etter løpet via `Data → Datautveksling eventor` og last opp resultatliste. 

## Løpsrapport
Etter løpet skal man levere løpsrapport til Norges Orienteringsforbund. Denne leveres digitalt i Eventor. Etter å ha lastet opp resultatlistene vil du i arrangementssiden i Eventor se at neste steg er å levere løpsrapporten. 

Du trenger å finne ut antall løpere i ulike aldergrupper for å levere inn løpsrapporten:
- Fra og med 21 år
- 17–20 år
- 13–16 år
- Til og med 12 år
- Småtroll
- Ukjent alder

Du kan telle disse ganske enkelt selv i løper-oversikten (velg listevisning og sorter etter Født-kolonnen). Du kan også telle dem ved å bruke spørringene under. Husk: spørringene må kjøres separat fra `Diverse → Spørring`. Resultatet av spørringene er antallet startede i hver alderkategori.

```sql
--Løpere over 21 år ↓
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and (year(date())-year(fodt) >= 21);

--Løpere mellom 17 og 20 år ↓
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and year(date())-year(fodt) < 21 and year(date())-year(fodt) >= 17;

--Løpere mellom 13 og 16 år ↓
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and year(date())-year(fodt) < 17 and year(date())-year(fodt) >= 13;

--Løpere opp til og med 12 år ↓
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and year(date())-year(fodt) < 13;

--Løpere med ukjent alder ↓
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and fodt is null) ;
```

## Terjes guide fra 2019
Terje Urfjell laget en fin [guide fra 2019 til bruk av eTiming for Agderkarusellen](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) som ligger på [kretsens hjemmesider](http://agderokrets.no). Det er veldig mye her som er nyttig for tidtaking til sommercup også. 
