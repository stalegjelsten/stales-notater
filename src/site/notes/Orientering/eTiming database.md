---
{"dg-publish":true,"permalink":"/Orientering/eTiming database/","title":"eTiming database","tags":["etiming","orientering"]}
---


# eTiming database
Databasen til [[Orientering/eTiming\|eTiming]] er i MS Access format (`.mdb`) og kan åpnes i programmet [MDB Viewer plus](http://www.alexnolan.net/software/mdb_viewer_plus.htm). MDB Viewer kan både lese og skrive til databasen, samt utføre spørringer. Du kan også kjøre spørringer fra [[Orientering/eTiming\|eTiming]] ved å bruke `Diverse → Spørring`.

## Databasens oppbygning med tabeller
- `name` er tabellen med alle løpere
- `class` er tabellen med klasser
- `cource` er tabellen med løyper
- `team` er tabellen med klubber
- `ecard` er tabellen med stemplinger
- `controls` er tabellen med alle poster

>[!Warning] Bruk av anførselstegn i spørringer i eTiming
>Man er nødt til å bruke enkle anførselstegn, **'**, for å markere strenger. Doble anførselstegn blir ikke gjenkjent av eTiming

## Smarte tips

### Oppdatere klasseregisteret for fristart og åpne klasser
Setter alle klasser til intetkjønn og gir dem bruk brikketid + fristart.
```sql
update class set sex = 'X', freestart = True, direct = True;
``` 

### Gi tilfeldig løype til løpere i en klasse
Dersom man har ulike løyper i samme klasse (for eksempel med ulike gaflinger), så kan man tildele gaflinger til løperne tilfeldig ved hjelp av SQL. For at dette skal fungere må man ha [[Orientering/eTiming til Agderkarusell#Last inn løyper\|importert løypene i eTiming]] og notert seg hvilke løypenummer som hører til hver klasse.

I eksempelet under så skal klasse `H lang` tildeles løyper fra løypenummer 3 til og med 6. Endre på tallene 6 og 3 og klassenavnet for å passe til egen bruk

```sql
update name set cource = Int((6 - 3 + 1) * Rnd(id) + 3) where class in (select class.code from class where class.class = 'H lang');
```

#### Forklaring på spørringen
- Vi oppdaterer alle radene i tabellen `name` hvor feltet `class` har en klassekode som tilsvarer `H lang`
	- Siden koblingen mellom klassekoder og klassenavn er lagret i tabellen `class` er vi nødt til å bruke en ny `select`-spørring for å få tak i klassekoden
- Vi trekker et tilfeldig tall med `Rnd`. For å få ulike heltall for hver rad bruker vi `id` som parameter
- Det tilfeldige tallet er et tall mellom 0 og 1. Vi multipliserer derfor med differansen mellom øvre og nedre grense (+1), og vi legger til den nedre grensa. På denne måten får vi et tall mellom øvre og nedre grense når vi gjør om tallet til et heltall (`int`)
- Vi setter feltet `cource` til heltallet som vi beregnet i forrige steg

*Merk at denne metoden ikke gir like mange løpere i hver løype. Siden vi trekker tilfeldige tall så kan det være at det blir veldig mange i noen løyper, og ingen løpere i andre løyper. Man bør nok derfor justere løypenummere manuelt i etterkant.*


#### Bør testes til senere
```sql

update cource = 
select * from name order by Rnd(id) 
```


### Urangerte resultatlister for barn
```sql
update class set timingtype = 2 where class like 'N-%pen';
update class set timingtype = 1 where class like '%10%';
```

- `timingtype = 2` er urangert resultatliste uten tider
- `timingtype = 1` er urangert resultatliste med tider

### Få riktige kontingentnivåer til Agderkarusell
Bruk tre kontingentnivåer: 
1. Påmelding voksen 90 kr
2. Etteranmelding voksen 90 kr (dette nivået er egentlig ikke nødvendig)
3. Påmelding ungdom 50 kr

Sett kontingentnivå 1 i etiming til voksenkontingent og sett kontingentnivå 3 (spesialkontingent) til 50 kr.

Sett alle løpere under 17 år til ungdomskontingent og alle løpere som er 17 år eller eldre til voksenkontingent. Hvis ungdomsløpere melder seg på så *må du huske å sette `Født`-feltet til en dato som gir alder < 17 år*.

```sql
update name
	set feelevel = Switch(
		year(date())-year(fodt) < 17, 3,
		year(date())-year(fodt) >= 17, 1,
		fodt is null, 1
	);
```
