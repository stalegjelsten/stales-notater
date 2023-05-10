---
{"dg-publish":true,"permalink":"/Orientering/eTiming til Agderkarusell/","title":"eTiming til Agderkarusell","tags":["etiming","orientering"]}
---


# eTiming til Agderkarusell
Det er laget en fin [guide fra 2019 til bruk av eTiming for Agderkarusellen](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) som ligger på [kretsens hjemmesider](http://agderokrets.no).

Den guiden er utdatert på et par punkter. Jeg diskuterer disse nærmere under [[Orientering/eTiming til Agderkarusell#Kommentarer til guiden fra 2019\|#Kommentarer til guiden fra 2019]].

## Klasseoppsett, frister og kontingenter i Eventor
I Agderkarusellen så benyttes følgende klasseoppsett

| Løype | Klasser                  |
|:-----:| ------------------------ |
|   1   | N1, D1, H1               |
|   2   | D2, H2, D 11-12, H 11-12 |
|   3   | D3, H3, D 13-14, H 13-14 |
|   4   | D4, H4, D 15-16, H 15-16 |
|   5   | D5, H5, D 17-20, H 17-20 |

Under `påmeldingsavgifter og frister` i Eventor så velger du `Rediger, avansert visning`. Bruk kun 2 kontingentnivåer (slett de andre):
1. Påmeldingskontingent for voksen. 
	1. Kontingent 90 kr i 2023.
	2. Gjelder fra alder 17 år. Marker alle klassene hvor vi kan finne løpere over 17 år (alle direkteløyper + 17-20-klassene).
	3. Sett kontingentrekkefølge til 1.
2. Påmeldingskontingent ungdom
	1. Kontingent 50 kr i 2023.
	2. Gjelder opptil 16 år. Marker alle klassene hvor vi kan finne ungdomsløpere (alle direkteløyper + alle klasser opp til og med 16 år). 
	3. Sett kontingentrekkefølge til 3.

![Pasted image 20230510155041.png](/img/user/_resources/Pasted%20image%2020230510155041.png)

## Last inn påmeldte i eTiming og fiks klasser
I [[Orientering/eTiming\|eTiming]] velger du menyvalget `Data → Datautveksling eventor` og hent påmeldinger til løpet. Dette henter ned deltakere, klasser, klubber og informasjon om påmeldingskontingenter.

### Sette innstillinger for klassene
Vi er nødt til å gjøre noen endringer på klassene slik at det blir riktig Agderkarusellen:
- Vi ønsker å bruke brikketid og fristart i alle klasser.
- N1 / N-åpen skal ha urangert resultatliste uten tider. 
- D/H-10 skal ha urangert resultatliste. (*I 2023 finnes ikke D/H-10 i Agderkarusellen så du kan se bort fra denne*)
- Åpne løyper bør ha kjønnskode `X` for å unngå at eTiming gir oss feilmeldinger
- Du må selv vurdere om D1 og H1 skal ha rangerte tider. Hvis det er barn under 10 år i disse klassene så må enten klassene være uten tider, eller så må du flytte disse løperne over til N1 slik at de kommer på en resultatliste uten tid.

Du kan sette disse valgene for klassene manuelt, eller du kan gjøre det automatisk ved hjelp av SQL-spørringer.

#### Gjøre endringer på klassene manuelt
For å gjøre det manuelt så velger `Bruk alltid brikketid` og `Fristart` for hver klasse. For klasse N1 så endrer du `Tidtakingstype` til `Ikke vis tid`. For klasser som kan vise tid, men som ikke skal være rangerte kan du velge `Tidtakingstype` til `Ikke rangert`.

#### Gjøre endringer på klassene med SQL
For å bruke SQL åpner du menyvalget `Diverse → Spørring`. Nedenfor finner du tre spørringer – du er **nødt til å kjøre dem separat**. Kopier den første linjen nedenfor lim inn i SQL-vinduet (ta bort teksten `sql` i vinduet hvis det står der allerede) og trykk på `Kjør spørring` knappen. Gjenta for de neste linjene. *I 2023 så finnes ikke klasse D/H-10 i Agderkarusellen, du trenger derfor ikke kjøre den tredje spørringen.*

```sql
update class set sex = 'X', freestart = True, direct = True;
update class set timingtype = 2 where class like 'N-%pen' or class = 'N1';
update class set timingtype = 1 where class like '%10%';
```

![etiming-sql.png](/img/user/_resources/etiming-sql.png)

Se [[Orientering/eTiming database\|eTiming database]] for mer informasjon om databasens oppbygning og spørringer.

## Løyper og poster i Purple Pen og eTiming
Hovedprinsipp: **Bruk samme løypenummer i innbydelse, Purple Pen og eTiming**

I innbydelsene i 2023 så er løype 5 den lengste løypa og løype 1 er N-åpen.

### Klargjøring av løyper i Purple Pen
- Løyperekkefølgen i Purple Pen må være stigende. Altså skal løype 1 (N1 / N-åpen) ligge lengst til venstre. Endre rekkefølgen med menyvalget `Løyper → Løyperekkefølge`.
- Løypene **må** inneholde løypenummeret i navnet. Du kan gjerne kalle dem `Løype 1`, `Løype 2` osv.
- Hver løype **må** inneholde klasselista. Denne legger du inn under `Løype → Egenskaper` i feltet `Klasseliste / sekundær tittel`. Klasselista skal inneholde *navnet på hver klasse adskilt med komma*. *Det er svært viktig at navnene på klassene skrives på nøyaktig samme måte som i Eventor*, det vil som oftest si `D 11-12` med mellomrom mellom kjønnsbokstaven og aldergruppa.
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
- Sett det nederste feltet som heter `Kontingent` til 1 hvis det er en voksen og til 3 hvis det er ungdom under 17 år. 
- Hvis løperen er en ungdom under 17 år anbefaler jeg også at du skriver inn en fødselsdato som er mindre enn 17 år siden i `Født`-boksen, f.eks. 1.1.2015. Dette gjør at løperen får riktig kontingentnivå hvis vi gjør en automatisk spørring senere (se [[Orientering/eTiming til Agderkarusell#Fakturering\|#Fakturering]]).

## Tidtaking under løpet
Før løpet så starter du tidtakingsmodulen i eTiming og kobler til en MTR4 til avlesning. Nullstill MTR og synkroniser klokka fra PC til MTRen før du begynner å lese av brikker. [Guiden hos Agder o-krets fra 2019](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) har en god forklaring på hvordan du setter opp MTR, åpner tidtakingen og behandler disk/problemer som oppstår gjennom løpet.

Bruk [[Orientering/LiveRes for etiming\|LiveRes]] for å publisere liveresultater. 

## Resultater
Publiser resultater etter løpet via `Data → Datautveksling eventor` og last opp resultatliste. Når du først er inne i `Datautveksling eventor` kan det være lurt å hente ned `Klubber og navn for direktepåmelding` for klubber i Agder slik adressene på fakturaene blir riktige. 

## Fakturering

### Koble sammen Eventorkontingenter og eTiming
Opprett kobling mellom kontingenter i etiming og Eventor ved `Data → Eventor kontingenter`. I kolonnen `eTiming kontingentnivå 1,2,3` skriver du `1` for voksen påmeldingsavgift og `3` for ungdom. Husk å trykke på knappen `Oppdater etiming` i bunnen av dialogboksen for å gjøre endringene gjeldende for løperne.

### Slett ikke startede løpere
Ikke startede løpere skal heller ikke betale startkontingent i Agderkarusellen. Jeg mener det enkleste er å fjerne alle løpere som ikke har startet, da er du helt sikker på at de ikke kommer med på fakturaene eller teller i løpsrapporten. 
- Gå til løper-oversikten og listevisning
- Velg filtrering på `statusS`-feltet (se skjermbildet under)
- Velg `Påmedlt` (og ev. `Ikke startet` hvis det er et valg)
- Marker løperne du ønsker å slette ved å holde inne <kbd>shift</kbd> eller <kbd>ctrl</kbd>.
- Trykk på slett-knappen.

![Pasted image 20230510210142.png](/img/user/_resources/Pasted%20image%2020230510210142.png)

Hvis du heller ønsker å slette løperne med en SQL-kommando så vil følgende kommando slette alle med status Påmeldt, Ikke startet og Ledige.
```sql
delete from name where status like '[IVN]';
```

### Generer fakturaer
Generer fakturaer ved å åpne `Klubber` og deretter gå til menyvalg `Skriv ut → Kontingentrapport → Lagre hver faktura som egen pdf`. PDFer med fakturaer lagres nå i samme katalog som eTiming-databasefila. Du kan åpne denne katalogen ved å trykke på filbanen nederst i eTimingvinduet.
![filbane-etiming.png](/img/user/_resources/filbane-etiming.png)

**Kontroller at beløpene stemmer**. Alle ungdommer skal nå stå med spesialkontingent 50 kr og alle voksne med 90 kr.

Hvis ikke kontingentene er blitt riktige så kan du prøve med SQL-spørringer nedenfor. Disse gjør følgende:
- Setter kontingentnivå 1 til 90 kr for alle klasser
- Setter kontingentnivå 3 (spesialkontingent) til 50 kr for alle klasser
- Setter alle deltakere under 17 år til kontingentnivå 3 (spesialkontingent)
- Setter alle deltakere uten fødselsdato eller minst 17 år gamle til kontingentnivå 1

Husk: spørringene må kjøres én-og-én fra `Diverse → Spørring`.

```sql
update class set entryfee1 = 90, entryfee2 = 0, entryfee3 = 50;
update name set feelevel = 3 where year(date()) - year(fodt) < 17;

update name set feelevel = 1 where (fodt is null) or (year(date()) - year(fodt) >= 17);
```

Faktura PDFene sendes til kasserer på [okonomi@kok.no](mailto:okonomi@kok.no). PDFene *bør* ha arrangementets navn og dato + mottakerklubb i filnavnet.

## Løpsrapport
Etter løpet skal man levere løpsrapport til Norges Orienteringsforbund. Denne leveres digitalt i Eventor. Etter å ha lastet opp resultatlistene vil du i arrangementssiden i Eventor se at neste steg er å levere løpsrapporten. Jeg anbefaler du gjør deg ferdig med [[Orientering/eTiming til Agderkarusell#Fakturering\|#Fakturering]] og [[Orientering/eTiming til Agderkarusell#Slett ikke startede løpere\|sletter ikke startede løpere]] før du genererer løpsrapporten. På den måten blir antallet løpere som betaler kontingent korrekt, og antallet vi skal betale løpsavgift for til NOF blir korrekt.

Løpsrapporten består kun av antall løpere over og under 17 år. Du kan telle disse ganske enkelt selv i løper-oversikten (velg listevisning og sorter etter Født-kolonnen). Du kan også telle dem ved å bruke de to spørringene under. Husk: spørringene må kjøres separat fra `Diverse → Spørring`. Resultatet av spørringene er antallet startede over eller lik 17 år, og under 17 år.

```sql
select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and ((year(date())-year(fodt) >= 17) or (fodt is null)) ;

select count(*) from name where status like '[ABDSXZY]' and class not like 'NOCLAS' and year(date())-year(fodt) < 17;
```

## Kommentarer til guiden fra 2019
- s. 3 Klasser: fra 2023 skal Agderkarusellen også ha aldersklasser, se [[Orientering/eTiming til Agderkarusell#Klasseoppsett, frister og kontingenter i Eventor\|#Klasseoppsett, frister og kontingenter i Eventor]]
- s. 3 Påmeldingsavgifter og frister: Jeg anbefaler heller avansert visning og bruk av **kun 2** kontingentnivåer slik som vist i [[Orientering/eTiming til Agderkarusell#Klasseoppsett, frister og kontingenter i Eventor\|#Klasseoppsett, frister og kontingenter i Eventor]]
- s. 8: Post 100 brukes som oftest som *siste post i løypa*. Målpost er postkoden som står ved mållinjen. Det er som oftest 249.
- s. 8 Etter rettelse på løyper må du starte eTiming på nytt. Det kan være at dette stemmer, men eTiming har nå et `Last inn løyper på nytt`-valg under tidtakingen. Prøv det først før du starter på nytt.
- s. 10 Informasjon om klasse: Jeg anbefaler heller at du følger rådene i [[Orientering/eTiming til Agderkarusell#Sette innstillinger for klassene\|#Sette innstillinger for klassene]]
