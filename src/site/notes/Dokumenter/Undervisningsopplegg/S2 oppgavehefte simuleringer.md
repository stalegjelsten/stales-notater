---
{"dg-publish":true,"permalink":"/Dokumenter/Undervisningsopplegg/S2 oppgavehefte simuleringer/","title":"Simulering av sannsynlighet i Python","tags":["prøver"]}
---


Ifølge lærerplanen skal dere *simulere utfall i […] ulike statistiske fordelinger*, dette kan vi gjøre ved hjelp av simuleringer i Python.

## Prinsipper for simuleringer
Vi bruker ofte *Monte Carlo*-simuleringer i programmer for å finne sannsynligheter som er vanskelig å bestemme ved regning. Prinsippet for slike simuleringer er:

1. Du definerer en hendelse $A$
2. Du gjennomfører et stokastisk forsøk $N$ ganger
3. Du teller antall ganger $A$ inntreffer og kaller denne summen for $m$
4. Du beregner sannsynligheten ved: $P(A) \approx \frac{m}{N}=\frac{\text{antall gunstige}}{\text{antall mulige}}$

Dette er imidlertid ikke den ekte sannsynligheten, men $m/N$ gir en veldig god tilnærming når $N$ er høy. Prøv deg gjerne frem med stadig høyere $N$ (for eksempel 10000, 100 000, 1 000 000 og så videre), men stopp når du merker at programmet tar lang tid å kjøre. Du bør også sjekke at den beregnede sannsynligheten holder seg ganske stabil ved å kjøre programmet flere ganger.

## Å trekke fra en statistisk fordeling
Vi kan trekke ut en tilfeldig prøve fra mange ulike statistiske fordelinger. I S2 skal vi fokusere på:

- Uniform sannsynlighetsfordeling: *alle utfallene er like sannsynlige.*
- Binomisk sannsynlighetsfordeling: *Vi teller antallet suksesser i løpet av $n$ delforsøk, der alle delforsøkene er uavhengige og har samme sannsynlighet for suksess $p$.*
- Hypergeometrisk sannsynlighetsfordeling: *Vi har to typer objekter og trekker uten tilbakelegging.*
- Normalfordeling: *utfall nær forventningsverdien er mye mer sannsynlige.*

Vi bruker funksjoner fra bibliotekene `random` og `numpy.random` for å gjøre uttrekk fra ulike sannsynlighetsfordelinger. Vi skriver `import random` i toppen av programmene våre for å importere hele `random`-biblioteket, eller vi kan bruke `from random import gauss` for å kun importere normalfordelingsfunksjonen.

I alle de følgende eksemplene så vil variabelen `tilfeldig_tall` inneholde resultatet av et stokastisk forsøk med den respektive sannsynlighetsfordelingen.

### Trekke tilfeldig heltall
For å trekke et tilfeldig heltall i intervallet $[1 , 6]$ (fra og med 1, til og med 6) så kan du bruke `random.randint(a,b)`.

```python
import random
tilfeldig_tall = random.randint(1,6)
```

### Trekke tilfeldig desimaltall
For å trekke et tilfeldig desimaltall i intervallet $[0 , 1 \rangle$ så kan du bruke `random.random()`. Hvis du trenger å ha et tilfeldig desimaltall i intervallet $[5, 15\rangle$ så kan bare gange det tilfeldige tallet med 10 og legge til 5:

```python
import random
tilfeldig_tall = random.random()
tilfeldig_tall2 = 10 * random.random() + 5
```

### Trekke fra normalfordeling
For å trekke et tilfeldig tall fra en normalfordeling med forventningsverdi $\mu=180$ og standardavvik $\sigma=7$ så kan du bruke `random.gauss(mu, sigma)`.

```python
import random
tilfeldig_tall = random.gauss(180, 7)
```

### Trekke fra binomisk fordeling
Vi bruker `numpy.random.binomial(n, p)` for å trekke fra en binomisk fordeling med antall $n=\texttt{n}$ og sannsynlighet for suksess $p=\texttt{p}$.

For å simulere antallet frø som spirer hvis vi planter 50 frø med sannsynlighet 0,8 for å spire kan vi bruke:

```python
import numpy as np
tilfeldig_tall = np.random.binomial(50, 0.8)
```

### Trekke fra hypergeometrisk fordeling
For å trekke et tilfeldig tall fra en hypergeometrisk fordeling må vi bruke `numpy.random.hypergeometric(n_1, n_2, k)`. Vi importerer biblioteket med `import numpy as np` også bruker vi funksjonen som vist under med `np.random.hypergeometric()`. 

I eksempelet under så har vi 20 fotballspillere ($n_{1}=20$) og 30 volleyballspillere ($n_2=30$). I vårt stokastiske forsøk så skal vi trekke ut 3 tilfeldige personer ($k=3$) og telle hvor mange av dem som er fotballspillere (type 1).

```python
import numpy as np
tilfeldig_tall = np.random.hypergeometric(20, 30, 3)
```

### Trekke fra en liste
Vi bruker `random.choice(navn_på_liste)` for å trekke et tilfeldig element fra en liste. 

La oss si at du har kuler med tallene $12, 23$ og $34$ i en bolle. Da kan du trekke en tilfeldig kule med `random.choice()`.
```python
import random
liste = [12, 23, 34]
tilfeldig_tall = random.choice(liste)
```

Eller la oss si at du har to bananer, ett eple og en ananas i en fruktskål. Da kan du trekke en tilfeldig frukt med `random.choice()`.
```python
import random
liste = ["banan", "banan", "eple", "ananas"]
tilfeldig_frukt = random.choice(liste)
```

Hvis vi skal trekke 2 frukter uten tilbakelegging så kan vi bruke `random.sample(liste, antall)`.
```python
import random
liste = ["banan", "banan", "eple", "ananas"]
tilfeldige_frukter = random.sample(liste, 2)    // Vi trekker to frukter
```

Vær oppmerksom på at `tilfeldige_frukter` i dette tilfellet er en ny liste, slik at den første frukten er lagret i `tilfeldige_frukter[0]` og den andre frukten er lagret i `tilfeldige_frukter[1]`, den tredje frukten er lagret i `tilfeldige_frukter[2]` og så videre.

### Tips for simuleringer av stokastiske forsøk i S2

>[!tip] Lage en simulering fra stokastisk forsøk
>
>En simulering i S2 bør **"alltid"** ha med:  
>
>- Antall delforsøk (for eksempel `N = 1000`)
>- Antall gunstige utfall = 0 (`antall_gunstige = 0`)
>- En løkke. Som oftest `for i in range(N):`
>- Inni løkka må vi gjøre en test for å sjekke om vi har et gunstig utfall, for eksempel `if (kjoretid < 30):`
>- Hvis testen er sann så legger vi til 1 på antall gunstige: `antall_gunstige += 1`
>- En utregning av den estimerte sannsynligheten ved å ta `antall_gunstige / N`

## Oppgaver 

### Oppgave 1 – Antall seksere med terning
```python
import random

N = 1000
antall_gunstige = 0

for i in range(N):
	terningkast = random.randint(1, 6)
	if terningkast == 6:
		antall_gunstige += 1
print(f"Vi fikk {antall_gunstige} seksere på {N} terningkast."),  

ssh = antall_gunstige / N
print(f"Sannsynligheten for å få en sekser er omtrent {ssh * 100:.2f} %.")
# {ssh * 100:.2f} tar desimaltallet ssh og multipliserer med 100 for å gjøre 
# det om til prosent sannsynlighet. Deretter viser vi tallet på skjermen
# med 2 desimaler ved å skrive :.2f inni krøllparentesen.
```

a) Opprett en ny Python-fil og skriv inn programmet ovenfor. Kjør programmet.
b) Hvorfor må `antall_gunstige = 0` stå før `for`-løkka, mens `terningkast = randint(1, 6)` må stå inni løkka?
c) Gå gjennom programmet linje-for-linje og *skriv* en kort forklaring på hva som skjer.
d) Gir simuleringen et godt estimat for den sanne sannsynligheten (bør være 16,66… %)? Endre på `N` slik at du får gode resultater.

> [!fasit]-
>
> a) –
> b) Inni løkka gjør vi et stokastisk forsøk: vi kaster terningen. Vi må ha terningkastet inni løkka for å sørge for at vi får `N` (1000) ulike terningkast. `antall_gunstige` er en variabel som teller hvor mange ganger vi har fått 6. Hvis vi setter denne inni løkka så nullstiller vi telleren hver gang slik at vi ikke får telt opp antall ganger vi fikk 6.
> c) 
>   ```python
>   import random        # importerer bibliotek
>   
>   N = 1000             # antall forsøk
>   antall_gunstige = 0  # teller hvor mange gunstige utfall
>   
>   for i in range(N):   # løkke som kjører N ganger
>   	terningkast = random.randint(1, 6)   # et terningkast
>   	if terningkast == 6:                 # hvis vi fikk 6 på terningen
>   		antall_gunstige += 1             # øk antall_gunstige med 1
>   print(f"Vi fikk {antall_gunstige} seksere på {N} terningkast."),  
>   
>   ssh = antall_gunstige / N     # beregn sannsynligheten
>   print(f"Sannsynligheten for å få en sekser er omtrent {ssh * 100:.2f} %.")
>   ```
> d) Vi kan øke `N` til for eksempel 10 000 000 for å få et bedre estimat.

### Oppgave 2 – Summen av terninger
Bruk simuleringer i Python til å estimere sannsynligheten for:

a) Summen av 2 terningkast er 9 eller mer
b) Summen av 2 terningkast er delelig på 2.

>[!tip] Tips til oppgaven
>
>- Det er lurt å gjøre to terningkast inne i løkka og lagre resultatene i to ulike variabler, for eksempel `terning1 = random.randint(1, 6)` og `terning2 = random.randint(1, 6)`
>- For å sjekke om summen er 9 eller mer kan du gjøre en av følgende sammneligninger
>	- `if (terning1 + terning2 >= 9):`
>	- `if (terning1 + terning2 > 8):`
>- For å sjekke om summen av to terningkast er delelig på 2 så kan vi sjekke om resten etter delingen er null. (`25 % 4` gir oss svaret 1, siden $\frac{25}{7}$ gir oss 6 med 1 i rest)
>	- `if ((terning1 + terning2) % 2 == 0):`

>[!fasit]-
> 
> ```python
> import random
> N = 10_000_000
> antall_gunstige_a = 0
> antall_gunstige_b = 0
> for i in range(N):
>     terning1 = random.randint(1, 6)
>     terning2 = random.randint(1, 6)
>     if (terning1 + terning2 >= 9):
>         antall_gunstige_a += 1
>     if (terning1 + terning2) % 2 == 0:
>         antall_gunstige_b += 1
> ssh_a = antall_gunstige_a / N
> ssh_b = antall_gunstige_b / N
> ```
> 
> a) Sannsynligheten er omtrent 27,7 %.
> b) Sannsynligheten er omtrent 50 %

### Oppgave 3 – Normalfordelt høyde
Vi antar at høyden til menn er normalfordelt med $\mu=180 \, \text{cm}$ og $\sigma=7 \, \text{cm}$.
```python
from random import gauss
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
print(gauss(180, 7))
```

a) Forklar hva programmet ovenfor gjør.
b) Lag en simulering som beregner sannsynligheten for at en tilfeldig trukket mann er over 189 cm.
c) Lag en simulering som beregner sannsynligheten for at en tilfeldig trukket mann er mellom 170 og 182 cm.

>[!tip] Kombinere sammenligninger i if-setninger
>
>La oss si at vi har høyden til en mann lagret i variabelen `hoyde`. Da kan vi sjekke om denne er mellom 170 og 182 cm ved å sjekke kombinere to sammenligninger:
>```python
>if ((hoyde > 170) and (hoyde < 182)):
>```
>Siden vi bruker `and` så må høyden både være over 170 og under 182. 
>
>Vi kunne også testet om høyden var over 189 eller under 165 ved å gjøre
>```python
>if ((hoyde > 189) or (hoyde < 165)):
>```

>[!fasit]-
>
> a) Programmet trekker 8 tilfeldige menn fra normalfordelingen skriver ut høydene deres i cm.
> b) 9,9 %
> c) 53,6 %
> 
> ```python
> from random import gauss
> 
> N = 10_000_000
> antall_gunstige_b = 0
> antall_gunstige_c = 0
> 
> for i in range(N):
>     hoyde = gauss(180, 7)
>     if hoyde > 189:
>         antall_gunstige_b += 1
>     if (hoyde > 170) and (hoyde < 182):
>         antall_gunstige_c += 1
> 
> ssh_b = antall_gunstige_b / N
> ssh_c = antall_gunstige_c / N
> print(f"Sannsynligheten for at høyden er minst 189 cm er omtrent {ssh_b*100:.2f} %.")
> print(f"Sannsynligheten for at høyden er mellom 170 og 182 cm er omtrent {ssh_c*100:.2f} %.")
> ```

### Oppgave 4 – Ståles kjøretid til jobb
Hvis Ståle kjører til jobb regner han med at kjøretiden er normalfordelt med forventningsverdi 34 minutter og standardavvik 3 minutter. Han har skrevet programmet nedenfor som sier hvor lang tid kjøreturen tar en tilfeldig morgen.

```python
from random import gauss
kjoretid = gauss(34, 3)
print(f"Du bruker {kjoretid} minutter til jobb!")
```

Ta utgangspunkt i koden ovenfor og bruk simuleringer i Python til å bestemme hvor ofte Ståle bruker mindre enn 30 minutter.

>[!fasit]-
>
> Videoforklaring av oppgaven (+ noen flere oppgaver) ligger på [https://youtu.be/OzQojxn7j8c](https://youtu.be/OzQojxn7j8c)  
> 
> Man kan for eksempel bruke et program lignende dette.
> ```python
> from random import gauss
> 
> N = 100_000                    # antall forsøk
> antall_gunstige = 0            # starter en teller
> 
> for i in range(N):             # gjør N forsøk
>     kjoretid = gauss(34,3)     # trekk fra normalford.
>     if kjoretid < 30:          # Hvis kjøretiden < 30 min.
>         antall_gunstige += 1   # øker vi antall gunstige
> 
> ssh_prosent = antall_gunstige / N * 100
> 
> print(f"Det er omtrent {ssh_prosent:.2f} % sannsynlighet"
>       f"for at Ståle bruker mindre enn 30 minutter")
> ```
> 
> **Ved å kjøre programmet flere ganger ser det ut til at sannsynligheten er omtrent $9{,}1 \,\%$ for at Ståle bruker mindre enn 30 minutter til jobb.**


### Oppgave 5 – Trekke frukt fra fruktbolle
Ta utgangspunkt i koden under for denne oppgaven. Programmet trekker to frukter fra listen `frukter`. Du kan justere på `N` slik at det passer.

```python
import random

N = 1000
antall_gunstige = 0

frukter = ["banan", "banan", "banan", "ananas", "ananas", "eple", "appelsin", "klementin", "klementin"]

for i in range(N):
    tilfeldige_frukter = random.sample(frukter, 2)
```

> [!tip] Hente ut elementer fra lister
> `tilfeldige_frukter` er en liste med de to fruktene som vi trakk ut. Vi bruker `tilfeldige_frukter[0]` for å hente ut elementet i posisjon 0 i lista (i Python så er posisjon 0 = det første elementet), og vi kan bruke `tilfeldige_frukter[1]` for å hente ut det andre elementet.

a) Lag en simulering som beregner sannsynligheten for at de to fruktene du trekker er like. \
   Bruk en `if`-setning som sjekker om de to fruktene er like, og deretter øker du `antall_gunstige` med 1.
b) Lag en simulering som beregner sannsyligheten for å trekke 3 like frukter dersom man trekker 3. 
c) Lag en simulering hvor du trekker 3 frukter. Beregn sannsynligheten for at det samlede antallet bokstaver i de tre fruktene er mindre enn 17.


> [!tip] Bruke `len` for å finne antall bokstaver
> Vi kan bruke `len` til å finne lengden av et objekt.
>
> ```python
> drikke = "coca-cola"
> antall_bokstaver = len(drikke)   # dette gir antall_bokstaver => 9
> ```
> 
> Vær imidlertid klar over at hvis du gjør `len(frukter)` så teller `len` antall elementer i lista `frukter` og du får svaret 9.


>[!fasit]-
>
> https://youtu.be/PYQkEPucMfo
>
> a) Omtrent 14 %.
>    ```python
>    import random
>    
>    N = 100000
>    antall_gunstige = 0
>    
>    frukter = ["banan", "banan", "banan", "ananas", "ananas", "eple", "appelsin", "klementin", "klementin"]
>    
>    for i in range(N):
>        tilfeldige_frukter = random.sample(frukter, 2)
>        if tilfeldige_frukter[0] == tilfeldige_frukter[1]:
>            antall_gunstige += 1
>    
>    ssh = antall_gunstige / N
>    
>    print(f"Sannsynligheten for å trekke to like frukter er omtrent {ssh*100:.1f} %.")
>    ```
> 
> b) Omtrent 1,2 %
>    ```python
>        tilfeldige_frukter = random.sample(frukter, 3)
>        if tilfeldige_frukter[0] == tilfeldige_frukter[1] == tilfeldige_frukter[2]:
>    ```
> 
> c) Omtrent 20,3 %
>    ```python
>    import random
>    
>    N = 1000000
>    antall_gunstige = 0
>    
>    frukter = ["banan", "banan", "banan", "ananas", "ananas", "eple", "appelsin", "klementin", "klementin"]
>    
>    for i in range(N):
>        tilfeldige_frukter = random.sample(frukter, 3)
>        antall_bokstaver = len(tilfeldige_frukter[0]) + len(tilfeldige_frukter[1]) + len(tilfeldige_frukter[2])
>        if antall_bokstaver < 17:
>            antall_gunstige = antall_gunstige + 1
>    
>    ssh = antall_gunstige / N
>    print(f"Sannsynligheten for at antall bokstaver i de tre fruktene er mindre enn 17 er omtrent {ssh * 100:.2f} %.")
>    ```

### Oppgave 6 – Høyden til 2 år gamle jenter og gutter
*Eksamensoppgave fra eksamen høst 2023*.

Høyden $X$ til en tilfeldig valgt jente på 24 måneder er tilnærmet normalfordelt med forventningsverdi $E(X) = 87$ cm og standardavvik $\text{SD}(X) = 3{,}3$ cm.

Høyden $Y$ til en tilfeldig valgt gutt på 24 måneder er tilnærmet normalfordelt med forventningsverdi $E(Y) = 88$ cm og standardavvik $\text{SD}(Y) = 3{,}1$ cm.

Lag et program som du kan bruke til å anslå sannsynligheten for at høyden til et tilfeldig valgt barn på 24 måneder er mindre enn 84 cm. Gå ut ifra at det er like mange jenter som gutter i populasjonen.

>[!tip] Hvordan simulere tilfeldig gutt eller jente?
>
> Denne simuleringen bør vi gjøre i to steg:
>
> 1. Først finner vi ut om vi har trukket en gutt eller en jente
> 2. Deretter trekker vi fra riktig normalfordeling
>
> ```python
> tilfeldig_tall = random.randint(1,2)
> 
> if tilfeldig_tall == 1:
> 	# trekker ei tilfeldig jente fra populasjonen
> 	hoyde = random.gauss(forventning_jente, standardavvik_jente)
> else:
> 	# trekker en tilfeldig gutt fra populasjonen
> 	hoyde = random.gauss(forventning_gutt, standardavvik_gutt)
> ```

>[!fasit]-
>
> ```python
> import random
> 
> forventning_jente = 87
> standardavvik_jente = 3.3
> forventning_gutt = 88
> standardavvik_gutt = 3.1
> 
> antall_gunstige = 0
> N = 10000 # gjør 10000 trekk
> grenseverdi = 84
> 
> for i in range(N):
>     # gjør det tilfeldig om vi trekker en jente eller gutt
> 	tilfeldig_tall = random.randint(1,2)
> 
>     if tilfeldig_tall == 1:
> 		# trekker ei tilfeldig jente fra populasjonen
>         hoyde = random.gauss(forventning_jente, standardavvik_jente)
>     else:
> 		# trekker en tilfeldig gutt fra populasjonen
>         hoyde = random.gauss(forventning_gutt, standardavvik_gutt)
> 
>     if hoyde < grenseverdi:
>         antall_gunstige += 1
> 
> sannsynlighet = antall_gunstige / N
> 
> print(f"Sannsynligheten for at barnet er mindre enn {grenseverdi} cm ved 24 måneder er omtrent {sannsynlighet:.4f}.")
> ```
> 
> **Sannsynligheten er omtrent 0,14 for at et tilfeldig valgt barn på 24 måneder er under 84 cm.**


### Oppgave 7 – Gjennomsnittskarakter fra skoler
*Eksamensoppgave fra eksamen vår 2023.*

Forskere ønsker å undersøke matematikkunnskapene til elever i videregående skole. Elever fra tre store skoler skal være med i undersøkelsen.

Karakterstatistikk fra de tre skolene viser at karakterene i matematikk er tilnærmet normalfordelt. Tabellen nedenfor viser forventningsverdi og standardavvik for hver av de tre skolene.

| Skole   | Forventningsverdi | Standardavvik |
| ------- |:-----------------:|:-------------:|
| Skole A |        3,8        |      1,2      |
| Skole B |        3,4        |      1,4      |
| Skole C |        4,1        |      1,1      |

Forskerne skal trekke ut 20 elever. For hver elev de skal trekke, trekker de først en tilfeldig skole og deretter en tilfeldig elev fra den skolen.

a) Lag et program som simulerer gjennomsnittskarakteren til 20 elever som er valgt ut på denne måten.
b) Bruk simuleringer til å estimere sannsynligheten for at karaktersnittet til de 20 elevene er høyere enn 4. 

>[!fasit]-
>
> **Oppgave a**   
> ```python
> from random import randint, gauss 
> # henter nødvendige pakker for uniform fordeling og normalfordeling 
> 
> n = 20
> sum_karakterer = 0
> for i in range(n):
>     # trekker et tilfeldig tall fra 1 til 3. Dette tilsvarer
>     # skole A, B og C
>     skole = randint(1,3)
>     if skole == 1:
>         # hvis det tilfeldige tallet er 1, så skal vi trekke 
>         # tilfeldig elev fra skole A. I dette tilfellet har 
>         # normalfordelingen my = 3.8 og sigma = 1.2             
>         # # vi trekker en tilfeldig elev med gauss(mu, sigma)
>         elev = gauss(3.8, 1.2)
>     elif skole == 2:
>         elev = gauss(3.4, 1.4)
>     else:
>         elev = gauss(4.1, 1.1)
>     # vi legger til elevens karakter på summen
>     sum_karakterer += elev
> 
> print(f"Gjennomsnittskarakteren til de {n} elevene er {sum_karakterer/n:.3f}.")
> ```
> 
> ### 2-5b
> ```python
> from random import randint, gauss 
> # henter nødvendige pakker for uniform fordeling og normalfordeling 
> 
> N = 10_000
> antall_gunstige = 0
> for j in range(N):
>     n = 20
>     sum_karakterer = 0
>     for i in range(n):
>         # trekker et tilfeldig tall fra 1 til 3. 
>         # Dette tilsvarer skole A, B og C
>         skole = randint(1,3)
>         if skole == 1:
>             # hvis det tilfeldige tallet er 1, så skal vi trekke 
>             # tilfeldig elev fra skole A. I dette tilfellet har 
>             # normalfordelingen my = 3.8 og sigma = 1.2             
>             # vi trekker en tilfeldig elev med gauss(mu, sigma)
>             elev = gauss(3.8, 1.2)
>         elif skole == 2:
>             elev = gauss(3.4, 1.4)
>         else:
>             elev = gauss(4.1, 1.1)
>         # vi legger til elevens karakter på summen
>         sum_karakterer += elev
>     if sum_karakterer/n > 4:
>         # hvis snittkarakteren er over 4 så har vi et gunstig utfall
>         antall_gunstige += 1
> 
> print(f"Etter {N} simuleringer estimerer jeg at sannsynligheten for at"
>       f"gjennomsnittskarakteren er over 4 til {antall_gunstige/N:.4f}.")
> ```
> 
> Jeg brukte $10\,000$ simuleringer og testet programmet noen ganger. Jeg så at estimatene mine lå mellom 0,200 og 0,210. Siden avvikene er små og programmet allerede bruker 6-7 sekunder på å kjøre, så velger jeg å ikke øke antall simuleringer, $N$, for å oppnå bedre nøyaktighet.
> 
> **Sannsynligheten for at gjennomsnittskarakteren til de 20 elevene er over 4 er estimert til 0,205 ved hjelp av programmet over.**

### Oppgave 8 – Hoppkonkurranse
Tre skihoppere skal delta i en hoppkonkurranse. 
Tabellen nedenfor viser forventningsverdi og standardavvik for lengden på et hopp for hver av de tre hopperne. Vi antar at lengden på hoppene er uavhengig og normalfordelt. Alle hopperne hopper ett hopp hver.

|        | Forventningsverdi | Standardavvik |
| :----: | :---------------: | :-----------: |
| Birger |     70 meter      |   20 meter    |
| Maren  |     80 meter      |    5 meter    |
| Espen  |     75 meter      |   10 meter    |

Bruk simulering og bestem sannsynligheten for at Maren hopper lengst.

>[!fasit]-
>
>Vi lager en simulering i Python hvor vi trekker hopplengder ut fra normalfordelingene til $B$, $M$ og $E$. Deretter sjekker vi om Marens hopp er det lengste hoppet.
>
>```python
>from random import gauss
>N = 100_000
>antall_gunstige = 0
>
>for i in range(N):
>    # Trekker hopplengder fra normalfordelingene
>    B = gauss(70, 20)
>    M = gauss(80, 5)
>    E = gauss(75, 10)
>
>    # Sjekker om Marens hopp er lengre enn både Espens og Birgers
>    if (M > B and M > E):
>        antall_gunstige += 1
>
>ssh = antall_gunstige / N
>
>print(f"Det er omtrent {ssh * 100:.2f} % sannsynlighet for at Maren hopper lengst i andre omgang")
>```
>
>Etter å ha kjørt programmet flere ganger ser jeg at sannsynligheten er stabil på omtrent 47,4 %.
>
>**Det er omtrent 47,4 % sannsynlighet for at Maren hopper lengst i andre omgang.**

### Oppgave 9 – Russens 17. mai-tog
I en by er det tre videregående skoler, som til sammen skal stille med 6 russ som skal bære russefanen i 17. mai-toget.

| Skole   | Antall rødruss | Antall blåruss |
| ------- |:--------------:|:--------------:|
| Skole A |       76       |       23       |
| Skole B |       65       |       2        |
| Skole C |       29       |       52       |

Russestyret har valgt en litt tungvint måte å velge ut hvem som skal gå i toget. Først skal de trekke en tilfeldig skole, og deretter trekker de 6 tilfeldige russ fra samme skole.

a) Gitt at vi skal trekke 6 tilfeldige russ fra skole A: Forklar hvorfor det vil passe med en hypergeometrisk sannsynlighetsmodell for å bestemme antallet rødruss blant de 6.
b) Bruk simuleringer til å estimere sannsynligheten for at minst 5 av de 6 russene er rødruss.
c) Bruk simuleringer til å estimere sannsynligheten for at alle russene er samme farge.

>[!fasit]-
>
> a) Det er et endelig antall russ på hver skole, og dette antallet er ikke veldig høyt (under 100). Vi har dermed trekning uten tilbakelegging og bruker hypergeometrisk sannsynlighetsmodell.
> b) Det er omtrent 53 % sannsynlighet for å trekke minst 5 rødruss.
> c) Det er omtrent 36,2 % sannsynlighet for at alle russene er samme farge.
> 
> ```python
> import numpy as np
> import random
> 
> N = 100_000
> antall_gunstige_b = 0   # til oppgave b
> antall_gunstige_c = 0   # til oppgave c
> k = 6                   # hvor mange skal vi trekke fra hver skole
> for i in range(N):
>     tilfeldig_skole = random.randint(1, 3)
>     if tilfeldig_skole == 1:
>         rodruss = np.random.hypergeometric(76, 23, k)
>         blaaruss = k - rodruss  # alle som ikke er rødruss er blåruss
>     elif tilfeldig_skole == 2:
>         rodruss = np.random.hypergeometric(65, 2, k)
>         blaaruss = k - rodruss
>     else:
>         rodruss = np.random.hypergeometric(29, 52, k)
>         blaaruss = k - rodruss
>     if rodruss >= 5:
>         antall_gunstige_b += 1
>     if (rodruss == 6) or (blaaruss == 6):
>         antall_gunstige_c += 1
> 
> ssh_b = antall_gunstige_b / N
> ssh_c = antall_gunstige_c / N
> print(f"Det er omtrent {ssh_b * 100:.2f} % sannsynlighet for å trekke minst 5 rødruss")
> print(f"Det er omtrent {ssh_c * 100:.2f} % sannsynlighet for at alle russene har samme farge")
> ```

### Oppgave 10 – Antall kast før man får to like terninger på rad
Ane har en vanlig sekssidet terning. Hun ønsker å finne ut hvor mange ganger hun i gjennomsnitt må kaste terningen for å få det samme antallet øyne i to kast på rad.

Bruk simuleringer for å finne dette gjennomsnittet.

>[!fasit]-
>
> ```python
> from random import randint
> N = 100_000                        
> sum_øyne = 0                        # totalt antall øyne på terningene
> 
> for i in range(N):
>     t1 = randint(1,6)               # terningkast 1
>     t2 = randint(1,6)               # terningkast 2
> 
>     sum_øyne = sum_øyne + t1 + t2   # legger til resultatene til summen
>     while t1 != t2:
>         t1 = t2                     # flytter t2's verdi til t1
>         t2 = randint(1,6)           # ruller t2 på nytt
>         sum_øyne = sum_øyne + t2    # legger til nytt resultat til summen
> 
> EX = sum_øyne/N                     # forventningsverdi = snitt i det lange løp
> print(f"Jeg estimerer forventningsverdien til å være {EX:.3f} etter {N} simuleringer.")
> ```
> 
> Output: `Jeg estimerer forventningsverdien til å være 24.502 etter 100000 simuleringer.`
> 
> Etter å ha kjørt programmet flere ganger ser det ut til estimatet mitt er stabilt på rundt $24{,}5$. Det stemmer også godt med at forventningsverdien for en terning er $3{,}5$ og vi trenger i snitt $7$ kast før vi har fått to like på rad.
> 
> **Jeg estimerer forventningsverdien til summen av antall øyne før Ane får to like terninger på rad til å være 24,5.**
>  