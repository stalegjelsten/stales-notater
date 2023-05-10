---
{"dg-publish":true,"permalink":"/Orientering/eTiming til Agderkarusell/","title":"eTiming til Agderkarusell","tags":["etiming","orientering"]}
---


# eTiming til Agderkarusell

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
I [[Orientering/eTiming\|eTiming]] velger du menyvalget `Data → Datautveksling eventor` og hent påmeldinger til løpet.

Vi er nødt til å gjøre noen endringer på klassene:
- Vi ønsker å bruke brikketid og fristart i alle klasser.
- N1 / N-åpen skal ha urangert resultatliste uten tider. 
- ~~~D/H-10 skal ha urangert resultatliste.~~~ (*I 2023 finnes ikke D/H-10 i Agderkarusellen så du kan se bort denne foreløpig*)
- Åpne løyper bør ha kjønnskode `X` for å unngå feilmeldinger hele tiden
- Du må selv vurdere om D1 og H1 skal ha rangerte tider. Hvis det er barn under 10 år i disse klassen så anbefaler jeg at du flytter dem over til N1 slik at de kommer på en resultatliste uten tid.

Du kan sette alle disse valgene for klasse manuelt, eller du kan gjøre det automatisk ved hjelp av SQL-spørringer.

For å bruke SQL åpner du menyvalget `Ønsker → Spørring`. Nedenfor finner du tre spørringer – du er **nødt til å kjøre dem separat**. Kopier den første linjen nedenfor lim inn i SQL-vinduet (ta bort teksten `sql` i vinduet hvis det står der allerede) og trykk på `Kjør spørring` knappen. Gjenta for de neste linjene. *I 2023 så finnes ikke klasse D/H-10 i Agderkarusellen, du trenger derfor ikke kjøre den tredje spørringen.*

```sql
update class set sex = 'X', freestart = True, direct = True;
update class set timingtype = 2 where class like 'N-%pen' or class = 'N1';
update class set timingtype = 1 where class like '%10%';
```

![etiming-sql.png](/img/user/_resources/etiming-sql.png)

## Løyper og poster i Purple Pen og eTiming
Hovedprinsipp: **Bruk samme løypenummer i innbydelse, Purple Pen og eTiming**

I innbydelsene i 2023 så er løype 5 den lengste løypa og løype 1 er N-åpen.

### Purple Pen klargjøring
- Løyperekkefølgen i Purple Pen må være stigende. Altså skal løype 1 (N-åpen ligge lengst til venstre). Endre rekkefølgen med menyvalget `Løyper → Løyperekkefølge`.
- Løypene må inneholde løypenummeret i navnet. Du kan gjerne kalle dem `Løype 1`, `Løype 2` osv.
- Hver løype **må** inneholde klasselista. Denne legger du inn under `Løype → Egenskaper` i feltet `Klasseliste / sekundær tittel`. Klasselista skal inneholde navnet på hver klasse adskilt med komma. *Det er svært viktig at navnene på klassene skrives på nøyaktig samme måte som i Eventor*, det vil som oftest si `D 11-12` med mellomrom mellom kjønnsbokstaven og aldergruppa.
- Eksporter `.xml` fil med `Fil → Lag IOF XML-fil`. **Velg IOF XML 3.0** som filtype i `Lagre som`-dialogboksen som hopper opp.
- Lagre også Purple Pen fila slik at du kan laste opp til [[Livelox\|Livelox]].

### eTiming import
- `Fil → Importer → Poster og løyper` (eller bruk venstremenyen)
- Velg `Behold course ID / course variation`. Da får løypene samme løypekode som rekkefølgen de hadde i Purple Pen (løype 1 får kode 1)
- Velg IOF XML-fila og pass på at filtypen her også er satt til `IOF XML 3.0`.
- Hvis du blir spurt om å slette andre løyper: svar ja.
- Når du blir spurt om målpost så kan du gjerne legge inn denne allerede. Vi pleier å bruke 249-postene som målposter, men du kan bruke hvilken som helst kode.
- Dobbeltsjekk at løypene nå har riktig løypekode sammenlignet med løypenummer i innbydelse.
- Åpne Klasse-oversikten og sjekk at hver klasse har fått riktige løypenummer.
- Tildel løyper til alle løpere ved å åpne klasse-oversikten og gå til menyvalget `Klass → Oppdater løypenr på løpere`

## Etteranmeldinger på løpet
>[!todo]
>Skriv mer her! Husk spesielt å legge inn født år på ungdom
>

## Tidtaking under løpet
Før løpet så starter du tidtakingsmodulen i eTiming og kobler til en MTR4 til avlesning. Nullstill MTR og synkroniser klokka fra PC til MTRen før du begynner å lese av brikker.

Bruk [[Orientering/LiveRes for etiming\|LiveRes]] for å publisere liveresultater. 

Publiser resultater etter løpet via `Data → Datautveksling eventor` og last opp resultatliste. Når du først er inne i `Datautveksling eventor` kan det være lurt å hente ned `Klubber og navn for direktepåmelding` for klubber i Agder slik adressene på fakturaene blir riktig. 

## Fakturering
Opprett kobling mellom kontingenter i etiming og Eventor ved `Data → Eventor kontingenter`. I kolonnen `eTiming kontingentnivå 1,2,3` skriver du `1` for voksen påmeldingsavgift og `3` for ungdom.

Generer fakturaer ved å åpne `Klubber` og deretter gå til menyvalg `Skriv ut → Kontingentrapport → Lagre hver faktura som egen pdf`. PDFer med fakturaer lagres nå i samme katalog som eTiming-databasefila. Du finner denne ved å trykke på filbanen nederst i eTimingvinduet.
![filbane-etiming.png](/img/user/_resources/filbane-etiming.png)

**Kontroller at beløpene stemmer**. Alle ungdommer skal nå stå med spesialkontingent 50 kr og alle voksne med 90 kr.

Hvis ikke kontingentene er blitt riktige så kan du prøve med følgende SQL-spørringer. Disse gjør følgende:
- Setter kontingentnivå 1 til 90 kr
- Setter kontingentnivå 3 (spesialkontingent) til 50 kr
- Setter alle deltakere under 17 år til kontingentnivå 3 (spesialkontingent)
- Setter alle deltakere uten fødselsdato eller minst 17 år gamle til kontingentnivå 1

```sql
update class set entryfee1 = 90, entryfee2 = 0, entryfee3 = 50;
update name set feelevel = 3 where year(date()) - year(fodt) < 17;
update name set feelevel = 1 where fodt is null;
update name set feelevel = 1 where year(date()) - year(fodt) >= 17;
```
