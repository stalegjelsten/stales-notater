---
{"dg-publish":true,"permalink":"/Orientering/eTiming til sommercup/","title":"eTiming til sommercup","tags":["etiming","orientering"]}
---


# eTiming til sommercup
Dette er ment som en oppskrift på hvordan man kan bruke [[Orientering/eTiming\|eTiming]] til tidtaking under KOKs sommercupløp. Oppskriften vil fungere både ved tidtaking under arrangementet (polling fra MTR) eller [[Orientering/eTiming med spooling av resultater\|spooling]] av resultater i etterkant av arrangementet.

## Om KOKs sommercup
Sommercupen er en rekke enkle o-løp gjennom sommeren. Løpene har status som nærløp og det tilbys vanligvis 4 løyper:

| Løype | Løypenavn | Klassenavn                  | Kortnavn   | Lengde  | 
|:-----:|:---------:| --------------------------- | ---------- | ------- | 
|   1   |  A-lang   | Herrer A-lang, Damer A-lang | H-AL, D-AL | 3,5–4,5 | 
|   2   |  A-kort   | Herrer A-kort, Damer A-kort | H-AK, D-AK | 2,5–3,5 |   
|   3   |     C     | Herrer C, Damer C           | H-C, D-C   | 2,0–2,5        | 
|   4   |     N     | Nybegynner                  | N          | 1,5–2,0        | 

Løype A-kort kan veldig gjerne både være ganske enkel (mye B-poster) og bør være lettløpt slik at «den eldre garde» får en god opplevelse i løypa.

Påmeldingskontingenten har vært kr 0 for KOKs løpere og 30 kr for løpere fra andre klubber som betales via Vipps til #89632.

## Klasseoppsett, frister og kontingenter i Eventor
Opprett klassene i Eventor. Jeg anbefaler å kopiere fra tidligere Sommercup for å få et passende oppsett. Navnene på klassene skal være som tabellen over. 

![](/img/user/_resources/klasseoppsett-sommercup.png)

Under `påmeldingsavgifter og frister` i Eventor så velger du `Rediger, avansert visning`. Bruk kun ett kontingentnivå (slett de andre).
- Navn på avgift: Påmeldingskontingent
- Beløp: 30 kr
- Til dato: Sett tidspunkt for påmeldingsfrist på Eventor
- Fra og til alder: La disse stå åpne
- Kontingentrekkefølge: sett denne til 20

Merk alle klassene slik at endringen blir gjeldende for alle og trykk `Lagre`.
![_resources/påmeldingskontingenter-sommercup-eventor.png](/img/user/_resources/p%C3%A5meldingskontingenter-sommercup-eventor.png)

## Last inn påmeldte i eTiming og fiks klasser
Opprett et nytt løp i [[Orientering/eTiming\|eTiming]] med riktig navn, dato og første starttid.

I [[Orientering/eTiming\|eTiming]] velger du menyvalget `Data → Datautveksling eventor` og hent påmeldinger til løpet. Dette henter ned deltakere, klasser, klubber og informasjon om påmeldingskontingenter.

### Sette innstillinger for klassene
Vi er nødt til å gjøre noen endringer på klassene slik at det blir riktig for Sommercupen:
- Vi ønsker å bruke brikketid og fristart i alle klasser.
- Nybegynner skal ha urangert resultatliste uten tider. 
- Nybegynner bør ha kjønnskode `X` for å unngå at eTiming gir oss feilmeldinger

Du kan sette disse valgene for klassene [[Orientering/eTiming til sommercup#Gjøre endringer på klassene manuelt\|manuelt]], eller du kan gjøre dem [[Orientering/eTiming til sommercup#Gjøre endringer på klassene med SQL\|automatisk ved hjelp av SQL-spørringer]].

#### Gjøre endringer på klassene manuelt
For å gjøre det manuelt så velger `Bruk alltid brikketid` og `Fristart` for hver klasse. For klasse Nybegynner så endrer du `Tidtakingstype` til `Ikke vis tid` og kjønnskoden til `X`.

#### Gjøre endringer på klassene med SQL
For å bruke SQL åpner du menyvalget `Diverse → Spørring`. Kopier alle linjene nedenfor og lim inn i SQL-vinduet (ta bort teksten `sql` i vinduet hvis det står der allerede) og trykk på `Kjør spørring` knappen. 

```sql
update class 
	set 
		sex = 'X', 
		entryfee1 = 30,
		entryfee2 = 30,
		entryfee3 = 30,
		freestart = True, 
		direct = True,
		timingtype = iif(
			class like 'N-%pen' or class = 'Nybegynner' or class = 'N', 2, 0 
		);
```

![/_resources/etiming-sql.png](/img/user/_resources/etiming-sql.png)

Se [[Orientering/eTiming database\|eTiming database]] for mer informasjon om databasens oppbygning og spørringer.

## Løyper og poster i Purple Pen og eTiming
For å få en feilfri import av løypene fra Purple Pen til eTiming så må Purple Pen fila klargjøres etter prinsippene som blir beskrevet under. Jeg anbefaler at løypelegger gjør denne jobben før hen sender løypa til tidtaker.

Hovedprinsipp: **Bruk samme løypenummer i innbydelse, Purple Pen og eTiming**

Jeg anbefaler å bruke oppsettet fra starten av dette dokumentet, der løype 1 er den lengste løypa og løype 4 er nybegynnerløypa.

### Klargjøring av løyper i Purple Pen
- Løyperekkefølgen i Purple Pen må være stigende. Altså skal løype 1 (A-lang) ligge lengst til venstre. Endre rekkefølgen med menyvalget `Løyper → Løyperekkefølge`.
- Løypene **bør** inneholde løypenummeret i navnet. Du kan gjerne kalle dem `Løype 1`, `Løype 2` osv.
- Hver løype **må** inneholde klasselista. Denne legger du inn under `Løype → Egenskaper` i feltet `Klasseliste / sekundær tittel`. Klasselista skal inneholde *navnet på hver klasse adskilt med komma*. *Det er svært viktig at navnene på klassene skrives på nøyaktig samme måte som **kortnavnet** i Eventor*, det vil som oftest si `H-AL`, `D-AL` osv.
- Eksporter `.xml` fil med `Fil → Lag IOF XML-fil`. **Velg IOF XML 3.0** som filtype i `Lagre som`-dialogboksen som hopper opp.
- Lagre også Purple Pen fila slik at du kan laste opp til [[Orientering/Livelox\|Livelox]].

### Import av løyper i eTiming
- `Fil → Importer → Poster og løyper` (eller bruk venstremenyen)
- Velg `Behold course ID / course variation`. Da får løypene samme løypekode som rekkefølgen de hadde i Purple Pen (løype 1 får kode 1)
- Velg IOF XML-fila og pass på at filtypen her også er satt til `IOF XML 3.0`.
- Hvis du blir spurt om å slette andre løyper: svar ja.
- Når du blir spurt om målpost så kan du gjerne legge inn denne allerede. Vi pleier å bruke 249-postene som målposter, men du kan bruke hvilken som helst kode.
- Dobbeltsjekk at løypene nå har riktig løypekode sammenlignet med løypenummer i innbydelse.
- Åpne klasse-oversikten og sjekk at hver klasse har fått riktige løypenummer.
- Tildel løyper til alle løpere ved å åpne klasse-oversikten og gå til menyvalget `Klasse → Oppdater løypenr på løpere`

## Startlister
>[!tip] Startnummer
>Det er lurt å tildele startnummer til alle løpere før løpet. Dette gjør det litt raskere å behandle løpere som går i mål med ukjente brikkenummer. Tildel startnummer med `Start → Startnr tildeling`.


Gå til menyvalget `Data → Datautveksling eventor` og last opp startliste til Eventor. Sjekk på Eventor at den ser korrekt ut.

### Skriv ut startlister
Du *bør* skrive ut startlister. Det gjør det enkelt for en funksjonær som står ved starten å krysse av hvem som faktisk starter løpet – da slipper man å lure på om det fremdeles er noen igjen ute i skogen eller ikke. 

Den som står ved starten *trenger ikke* skrive opp etteranmeldte manuelt. De som har etteranmeldt seg på samlingsplass kommer til å starte.

## Etteranmeldinger på løpet
Legg inn etteranmeldte på løpet ved å åpne løper-oversikten. 
- Trykk på `+`-tegnet i verktøylinja eller <kbd>ctrl</kbd> + <kbd>N</kbd> for legge til ny løper.
- Fyll inn navn, klasse, klubb og brikkenr. 
	- Hvis løperen skal låne brikke så kan du trykke på avkrysningsboksen merket `Brikke`. Da blir løperen merket med blå farge når hen kommer i mål slik at du vet at du skal samle inn leiebrikken igjen.
- Hvis løperen er under 21 år så anbefaler jeg også at du skriver inn fødselsdato (eller i det minste fødselsår) i `Født`-boksen, f.eks. 1.1.2015. Dette gjør at vi får riktig antall barn, ungdommer og voksne i løpsrapporten som skal leveres. 

## Tidtaking
Du kan velge å ha tidtaking under løpet (*polling*) eller ved å lese inn resultatene fra MTR4 i etterkant av løpet (*spooling*). Å ha tidtaking under løpet krever at en person har dette som arbeidsoppgave, men det gjør også at det blir mindre etterarbeid og det er mulig å tilby [[Orientering/LiveRes for etiming\|liveresultater]].

### Tidtaking under løpet
Før løpet så starter du tidtakingsmodulen i eTiming og kobler til en MTR4 til avlesning. Nullstill MTR og synkroniser klokka fra PC til MTRen før du begynner å lese av brikker. [Guiden hos Agder o-krets fra 2019](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) har en god forklaring på hvordan du setter opp MTR, åpner tidtakingen og behandler disk/problemer som oppstår gjennom løpet.

Bruk [[Orientering/LiveRes for etiming\|LiveRes]] for å publisere liveresultater. 

Etter at siste starttid er passert (kl 18.30) så gir du status `Ikke startet` på alle løpere som ikke har startet. 

>[!tip] Oversikt over løpere i skogen
>Trykk på `4. Under arrangementet` i venstremenyen og `Ikke fullførte løpere → ✔️`.

## Resultater
Publiser resultater etter løpet via `Data → Datautveksling eventor`. Kryss av for valget `Api nøkkel i opplasting` og last opp resultatliste. 

>[!tip] Manuell opplasting av resultater
>Hvis det ikke er mulig å gjøre Datautveksling med Eventor så kan det være at det fungerer å laste opp resultatene manuelt. For å gjøre dette må du:
>1. Lag en IOF XML 3.0 fil med resultatene ved å gå til `Data → Datautveksling Eventor`. I linjen  `Datautveksling fra nedlastede XML filer` velger du `Vis → Lag resultatlistefil`.
>2. Gå til løpet i `Eventor → Rediger → Dataoverføringer → Last opp resultatliste`
>3. Finn fram `iofres.xml` som ligger i databasemappa → `htmlfiler`.
{ #ed86ad}


## Løpsrapport
Etter løpet skal man levere løpsrapport til Norges Orienteringsforbund. Denne leveres digitalt i Eventor. Etter å ha lastet opp resultatlistene vil du i arrangementssiden i Eventor se at neste steg er å levere løpsrapporten. 

Du trenger å finne ut antall løpere i ulike aldergrupper for å levere inn løpsrapporten:
- Fra og med 21 år
- 17–20 år
- 13–16 år
- Til og med 12 år
- Småtroll
- Ukjent alder

Du kan telle disse ganske enkelt selv i løper-oversikten (velg listevisning og sorter etter Født-kolonnen). Du kan også telle dem ved å bruke SQL-spørringen nedenfor ved å lime inn hele spørringen i `Diverse → Spørring`. Resultatet er antallet startede i hver alderskategori.

```sql
select
	abs(sum((year(date())-year(fodt) >= 21 and status like '[ABDSXZY]' and class not like 'NOCLAS'))) as Over21,
	abs(sum((year(date())-year(fodt) >= 17) and (year(date())-year(fodt) <= 20) and status like '[ABDSXZY]' and class not like 'NOCLAS')) as 17til20,
	abs(sum((year(date())-year(fodt) >= 13) and (year(date())-year(fodt) <= 16) and status like '[ABDSXZY]' and class not like 'NOCLAS')) as 13til16,
	abs(sum((year(date())-year(fodt) <= 12) and status like '[ABDSXZY]' and class not like 'NOCLAS')) as Under12,
	abs(sum((fodt is null) and status like '[ABDSXZY]' and class not like 'NOCLAS')) as UkjentAlder
from name;
```

## Terjes guide fra 2019
Terje Urfjell laget en fin [guide fra 2019 til bruk av eTiming for Agderkarusellen](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) som ligger på [kretsens hjemmesider](http://agderokrets.no). Det er veldig mye her som er nyttig for tidtaking til sommercup også. 
