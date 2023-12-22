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
Dersom man har ulike løyper i samme klasse (for eksempel med ulike gaflinger), så kan man tildele gaflinger tilfeldig ved hjelp av SQL. Linja nedenfor tildeler en tilfeldig løype til alle løpere i klasse `H lang`. Løypenummeret er i dette eksempelet et tilfeldig heltall i intervallet $[3  , 6]$. Endre på tallene 6 og 3 og klassenavnet for å passe til egen bruk

```sql
update name set cource = Int((6 - 3 + 1) * Rnd(id) + 3) where class in (select class.code from class where class.class = 'H lang');
```

*Merk at denne metoden ikke gir like mange løpere i hver løype. Siden vi trekker tilfeldige tall så kan det være at det blir veldig mange i noen løyper, og ingen løpere i andre løyper. Man bør nok derfor justere løypenummere manuelt i etterkant.*

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
