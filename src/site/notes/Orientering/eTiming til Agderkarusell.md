---
{"dg-publish":true,"permalink":"/Orientering/eTiming til Agderkarusell/","title":"eTiming til Agderkarusell","tags":["etiming","orientering"]}
---


# eTiming til Agderkarusell
Det er laget en fin [guide fra 2019 til bruk av eTiming for Agderkarusellen](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) som ligger på [kretsens hjemmesider](http://agderokrets.no).

Den guiden er utdatert på et par punkter. Jeg diskuterer disse nærmere under [[Orientering/eTiming til Agderkarusell#Kommentarer til guiden fra 2019\|#Kommentarer til guiden fra 2019]].

## Klasseoppsett, frister og kontingenter i Eventor
I Agderkarusellen så benyttes følgende klasseoppsett 👇

| Løype | Klasser                  |
|:-----:| ------------------------ |
|   1   | N1, D1, H1               |
|   2   | D2, H2, D 11-12, H 11-12 |
|   3   | D3, H3, D 13-14, H 13-14 |
|   4   | D4, H4, D 15-16, H 15-16 |
|   5   | D5, H5, D 17-20, H 17-20 |

Legg inn klassene i Eventor. Pass på at `Kortnavn` til hver klasse stemmer overens med klassenavnet over. Navnene på hver klasse kan gjerne inneholde noe mer informasjon, slik at klassenavnet for eksempel kan være `D1 - Damer N-løype`. Det enkleste er å kopiere oppsett fra tidligere løp eller tidligere år – pass bare på at det ikke er kommet med noen nye klasser siden sist.

Under `Påmeldingsavgifter og frister` i Eventor så velger du `Rediger, avansert visning`. Bruk kun 2 kontingentnivåer (slett de andre):
1. Påmeldingskontingent for voksen. 
	1. Kontingent 90 kr i 2024.
	2. Gjelder fra alder 17 år. Marker alle klassene hvor vi kan finne løpere over 17 år (alle direkteløyper + 17-20-klassene).
	3. Sett kontingentrekkefølge til 1.
2. Påmeldingskontingent ungdom
	1. Kontingent 50 kr i 2024.
	2. Gjelder opptil 16 år. Marker alle klassene hvor vi kan finne ungdomsløpere (alle direkteløyper + alle klasser opp til og med 16 år). 
	3. Sett kontingentrekkefølge til 3.

![/_resources/eventor-kontingenter.png](/img/user/_resources/eventor-kontingenter.png)

## Last inn påmeldte i eTiming og fiks klasser
Opprett et nytt løp i [[Orientering/eTiming\|eTiming]] med riktig navn, dato og første starttid.

I [[Orientering/eTiming\|eTiming]] velger du menyvalget `Data → Datautveksling eventor` og hent påmeldinger til løpet. Dette henter ned deltakere, klasser, klubber og informasjon om påmeldingskontingenter.

### Sette innstillinger for klassene
Vi er nødt til å gjøre noen endringer på klassene slik at det blir riktig for Agderkarusellen:
- Vi ønsker å bruke brikketid og fristart i alle klasser.
- N1 / N-åpen skal ha urangert resultatliste uten tider. 
- D/H-10 skal ha urangert resultatliste. (*I 2023 finnes ikke D/H-10 i Agderkarusellen så du kan se bort fra denne*)
- Åpne løyper bør ha kjønnskode `X` for å unngå at eTiming gir oss feilmeldinger
- Du må selv vurdere om D1 og H1 skal ha rangerte tider. Hvis det er barn under 10 år i disse klassene så må enten klassene være uten tider, eller så må du flytte disse løperne over til N1 slik at de kommer på en resultatliste uten tid.

Du kan sette disse valgene for klassene manuelt, eller du kan gjøre det automatisk ved hjelp av SQL-spørringer.

#### Gjøre endringer på klassene manuelt
For å gjøre det manuelt så velger `Bruk alltid brikketid` og `Fristart` for hver klasse. For klasse N1 så endrer du `Tidtakingstype` til `Ikke vis tid`. For klasser som kan vise tid, men som ikke skal være rangerte kan du velge `Tidtakingstype` til `Ikke rangert`.

#### Gjøre endringer på klassene med SQL
For å bruke SQL åpner du menyvalget `Diverse → Spørring`. Kopier alle linjene nedenfor og lim inn i SQL-vinduet (ta bort teksten `sql` i vinduet hvis det står der allerede) og trykk på `Kjør spørring` knappen. Spørringen setter kjønnskoden til `X`, setter fristart og brikketid, samt påmeldingskontingenter 90 kr og 50 kr for alle klasser. Klasser med navn `N-åpen` eller `N1` blir satt som urangert resultatliste uten tider. Klasser med navn som inkluderer `10` blir satt som urangert resultatliste med tid.

```sql
update class 
	set 
		sex = 'X', 
		freestart = True, 
		direct = True,
		entryfee1 = 90,
		entryfee2 = 0,
		entryfee3 = 50,
		timingtype = iif(
			class like 'N-%pen' or class = 'N1', 2, iif(class like '%10%', 1, 0)
		);
```

![/_resources/etiming-sql.png](/img/user/_resources/etiming-sql.png)

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
Du *bør* skrive ut startlistene på papir. Det gjør det enkelt for en funksjonær som står ved starten å krysse av hvem som faktisk starter løpet – da slipper man å lure på om det fremdeles er noen igjen ute i skogen eller ikke. 

Den som står ved starten *trenger ikke* skrive opp etteranmeldte manuelt. De som har etteranmeldt seg på samlingsplass kommer til å starte.

## Etteranmeldinger på løpet
Legg inn etteranmeldte på løpet ved å åpne løper-oversikten. 
- Trykk på `+`-tegnet i verktøylinja eller <kbd>ctrl</kbd> + <kbd>N</kbd> for legge til ny løper.
- Fyll inn navn, klasse, klubb og brikkenr. 
	- Hvis løperen skal låne brikke så kan du trykke på avkrysningsboksen merket `Brikke`. Da blir løperen merket med blå farge når hen kommer i mål slik at du vet at du skal samle inn leiebrikken igjen.
- Sett det nederste feltet som heter `Kontingent` til 1 hvis det er en voksen og til 3 hvis det er ungdom under 17 år. 
- Det er veldig lurt å skrive inn en **fødselsår** i `Født`-boksen slik at vi både får riktig kontingentnivå (se [[Orientering/eTiming til Agderkarusell#Fakturering\|#Fakturering]]) og riktige aldergrupper til [[Orientering/eTiming til Agderkarusell#Løpsrapport\|løpsrapporten]].

## Tidtaking under løpet
Før løpet så starter du tidtakingsmodulen i eTiming og kobler til en MTR4 til avlesning. Nullstill MTR og synkroniser klokka fra PC til MTRen før du begynner å lese av brikker. [Guiden hos Agder o-krets fra 2019](http://www.orientering.no/media/filer_public/78/e3/78e35b05-4f16-4760-b6c4-edb28c884234/oppskrift_eventor_etiming_aaok_karusellen.pdf) har en god forklaring på hvordan du setter opp MTR, åpner tidtakingen og behandler disk/problemer som oppstår gjennom løpet.

Bruk [[Orientering/LiveRes for etiming\|LiveRes]] for å publisere liveresultater. 

## Resultater
Publiser resultater etter løpet via `Data → Datautveksling eventor`. Kryss av for valget `Api nøkkel i opplasting` og last opp resultatliste. 

Når du først er inne i `Datautveksling eventor` kan det være lurt å hente ned `Klubber og navn for direktepåmelding` for klubber i Agder slik adressene på fakturaene blir riktige. 


<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/orientering/e-timing-til-sommercup/#ed86ad" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



>[!tip] Manuell opplasting av resultater
>Hvis det ikke er mulig å gjøre Datautveksling med Eventor så kan det være at det fungerer å laste opp resultatene manuelt. For å gjøre dette må du:
>1. Lag en IOF XML 3.0 fil med resultatene ved å gå til `Data → Datautveksling Eventor`. I linjen  `Datautveksling fra nedlastede XML filer` velger du `Vis → Lag resultatlistefil`.
>2. Gå til løpet i `Eventor → Rediger → Dataoverføringer → Last opp resultatliste`
>3. Finn fram `iofres.xml` som ligger i databasemappa → `htmlfiler`.

</div></div>


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

![/_resources/etiming-merke-status.png](/img/user/_resources/etiming-merke-status.png)

Hvis du heller ønsker å slette løperne med en SQL-kommando så vil følgende kommando slette alle med status Påmeldt, Ikke startet og Ledige.
```sql
delete from name where status like '[IVN]';
```

### Generer fakturaer
Generer fakturaer ved å åpne `Klubber` og deretter gå til menyvalg `Skriv ut → Kontingentrapport → Lagre hver faktura som egen pdf`. PDFer med fakturaer lagres nå i samme katalog som eTiming-databasefila. Du kan åpne denne katalogen ved å trykke på filbanen nederst i eTimingvinduet.
![/_resources/filbane-etiming.png](/img/user/_resources/filbane-etiming.png)

**Kontroller at beløpene stemmer**. Alle ungdommer skal nå stå med spesialkontingent 50 kr og alle voksne med 90 kr.

Hvis ikke kontingentene er blitt riktige så kan du prøve med SQL-spørringer nedenfor. Disse gjør følgende:
1. Setter kontingentnivå 1 til 90 kr og kontingentnivå 3 (spesialkontingent) til 50 kr for alle klasser
2. Setter alle deltakere under 17 år til kontingentnivå 3 (spesialkontingent) og alle deltakere uten fødselsdato eller minst 17 år gamle til kontingentnivå 1

Det er viktig at de to spørringene kjøres én-og-én fra `Diverse → Spørring`.

```sql
update class set entryfee1 = 90, entryfee2 = 0, entryfee3 = 50;

update name
	set feelevel = Switch(
		year(date())-year(fodt) < 17, 3,
		year(date())-year(fodt) >= 17, 1,
		fodt is null, 1
	);
```

Faktura PDFene sendes til kasserer på [okonomi@kok.no](mailto:okonomi@kok.no). PDFene *bør* ha arrangementets navn og dato + mottakerklubb i filnavnet.

## Løpsrapport
Etter løpet skal man levere løpsrapport til Norges Orienteringsforbund. Denne leveres digitalt i Eventor. Etter å ha lastet opp resultatlistene vil du i arrangementssiden i Eventor se at neste steg er å levere løpsrapporten. Jeg anbefaler du gjør deg ferdig med [[Orientering/eTiming til Agderkarusell#Fakturering\|#Fakturering]] og [[Orientering/eTiming til Agderkarusell#Slett ikke startede løpere\|sletter ikke startede løpere]] før du genererer løpsrapporten. På den måten blir antallet løpere som betaler kontingent korrekt, og antallet vi skal betale løpsavgift for til NOF blir korrekt.

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

## Kommentarer til guiden fra 2019
Terje Urfjell laget en fin [guide fra 2019 til bruk av eTiming for Agderkarusellen](https://www.orientering.no/storage/Preview?id=b139d37c-a4e9-4f38-8037-df8ebaf125ec) som ligger på [kretsens hjemmesider](http://agderokrets.no). Det er veldig mye som fremdeles gjelder og den forklarer mange deler av tidtakinga svært godt. Her kommer mine kommentarer til hvilke deler av guiden du *ikke* bør følge:
- s. 3 Klasser: fra 2023 skal Agderkarusellen også ha aldersklasser, se [[Orientering/eTiming til Agderkarusell#Klasseoppsett, frister og kontingenter i Eventor\|#Klasseoppsett, frister og kontingenter i Eventor]]
- s. 3 Påmeldingsavgifter og frister: Jeg anbefaler heller avansert visning og bruk av **kun 2** kontingentnivåer slik som vist i [[Orientering/eTiming til Agderkarusell#Klasseoppsett, frister og kontingenter i Eventor\|#Klasseoppsett, frister og kontingenter i Eventor]]
- s. 8: Post 100 brukes som oftest som *siste post i løypa*. Målpost er postkoden som står ved mållinjen. Det er som oftest 249.
- s. 8 Etter rettelse på løyper må du starte eTiming på nytt. Det kan være at dette stemmer, men eTiming har nå et `Last inn løyper på nytt`-valg under tidtakingen. Prøv det først før du starter på nytt.
- s. 10 Informasjon om klasse: Jeg anbefaler heller at du følger rådene i [[Orientering/eTiming til Agderkarusell#Sette innstillinger for klassene\|#Sette innstillinger for klassene]]
