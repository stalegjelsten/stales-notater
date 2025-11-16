---
{"dg-publish":true,"permalink":"/Dokumenter/Generelle Pythontips/","title":"Generelle Pythontips","tags":["s2"]}
---


## Generelle Pythontips

### Kombinere tekst og tall i utskrifter

> [!tip] Bruk **f-strenger**!
>
> Det finnes flere måter å kombinere tekst og tall i Python, men *f-strenger* er den nyeste og mest presise måten å gjøre det på. Du kan velge andre løsninger, men jeg anbefaler f-strenger.
>
> 

En *f-streng* er en enkel måte å kombinere tekst og variabler i Python. Du skriver en `f` foran anførselstegnene som dette: `f"Tekststreng"`. Inni tekststrenger bruker du sløyfeparenteser `{ }` for å sette inn variabler.

```python
navn = "Sara"
alder = 17
print(f"Hei, jeg heter {navn} og er {alder} år.")
```

>[!danger] Hvis du vil gå din egen vei…
>
>Hvis du er helt sikker på at du ikke vil bruke *f-strenger* så kan du bruke
>```python
>print("Hei, jeg heter", navn, "og er", alder, "år.")
>``` 
> 
>Merk at det automatisk legges til mellomrom mellom variabler og tekst så lenge du ikke legger til `sep=""` i slutten av funksjonskallet. `sep` angir tegnet som skal settes mellom elementene.

#### Regnestykker og funksjoner i f-strenger

Du kan også gjøre regnestykker eller kalle funksjoner direkte inni sløyfeparentesene:

```python
a = 5
b = 3
print(f"Summen av {a} og {b} er {a + b}.")       
print(f"Kvadratroten av {a} er {a**0.5}.")         
print(f"Navnet i store bokstaver: {navn.upper()}")
```

#### Avrunding av tall

Ofte vil du vise tall med et bestemt antall desimaler, da kan du for eksempel bruke `:.2f` for å vise tallet med 2 desimaler. Du kan også gjøre det enklere å lese store tall ved å bruke `:_` – da grupperes sifrene i grupper på tre.

```python
tall = 3.14159
stortTall = 823719518232
print(f"Tallet er {tall:.2f}")   # => 3.14
print(f"Tallet er {tall:.4f}")   # => 3.1416
print(f"{stortTall:_}")          # => 823_719_518_232
```

### Feilsøking i Python-programmer
Når du skriver Python-kode, vil du ofte møte på feilmeldinger. Det er kjedelig å møte en feilmelding, men de er laget for å forklare deg hva som er problemet med programmet ditt. Med litt trening så klarer du å se hva som gikk galt og hvor i koden problemet oppstod.

Noen vanlige typer feil er:

- **`SyntaxError`**: Koden er skrevet på en måte som Python ikke forstår. For eksempel mangler det et kolon eller noen mellomrom. 
	- Hvis du får `EOL while scanning string literal` så har du mest sannsynlig glemt å avslutte en parentes eller tekststreng.
- **`NameError`**: Du prøver å bruke en variabel eller funksjon som ikke finnes. Som oftest har du feilstavet navnet på en variabel eller funksjon.
- **`TypeError`**: Du bruker en datatype på feil måte, f.eks. legger sammen en tekststreng og et tall.
- **`ValueError`**: Funksjonen får en verdi som har riktig type, men er ugyldig. Eksempel: `int("hei")`.
- **`IndexError`**: Du prøver å hente et element fra en liste som ikke finnes, f.eks. `liste[10]` når listen bare har 5 elementer.

> [!tip] Les feilmeldingen nøye!
>
> Les alltid feilmeldingen nøye. Nederst i meldingen står hvilken type feil det er, og rett over står hvilken linje i koden feilen oppstod på. Start feilsøkingen der – ofte er det bare en liten skrivefeil eller en verdi du ikke hadde tenkt over. 
> 
> Hvis du har glemt å *avslutte* en parentes eller en tekststreng så vil nesten alltid feilen ligge en linje eller to ovenfor linjenummeret i feilmeldingen.
