---
{"dg-publish":true,"permalink":"/Dokumenter/Undervisningsopplegg/S2 programmering av rekursive sammenhenger/","title":"Programmering av rekursive sammenhenger"}
---


Ifølge læreplanen skal dere utforske *rekursive sammenhenger* med programmering. En rekursiv sammenheng vil si at vi bruker ett ledd til å regne ut det neste leddet – for å regne ut $a_{n+1}$ så trenger vi først å ha regnet ut $a_{n}$.

## Oppgave 1
Gitt den aritmetiske tallfølgen $2,4,6,8,10,\dots$

a) Forklar den rekursive sammenhengen mellom leddene
b) Skriv ned en formel for den rekursive sammenhengen mellom $a_{n+1}$ og $a_{n}$
c) Skriv inn koden nedenfor og kjør programmet.
d) Forklar hvordan koden nedenfor fungerer

```python
a = 2 
d = 2
n = 10
for i in range(1, n + 1):
	print(f"a_{i} = {a}")
	a = a + d
```

>[!fasit]
>
>a) Hvert ledd er det forrige leddet pluss 2
>b) $a_{n+1}=a_{n}+2$
>c) –
>d) Vi definerer først startverdien `a`, differansen mellom leddene `d` og antall ledd `n`. Deretter lager vi en løkke som går fra 1 til og med `n` som skriver ut verdien av $a_{i}$. Inne i løkka endrer vi også på verdien av `a` i henhold til formelen vi fant i b), ved å legge på 2.

## Oppgave 2
Gitt den geometriske tallfølgen $2,4,8,16,32,\dots$

a) Forklar den rekursive sammenhengen mellom leddene
b) Skriv ned en formel for den rekursive sammenhengen mellom $a_{n+1}$ og $a_{n}$
c) Skriv et program som regner ut verdien av de 15 første leddene. Ta gjerne utgangspunkt i koden fra oppgave 1.

>[!fasit]
>
> a) Hvert ledd er det dobbelte av det forrige leddet
> b) $a_{n+1}=a_{n} \cdot 2$
> c) Se under.
> 
> ```python
>a = 2 
>k = 2
>n = 10
>for i in range(1, n + 1):
>	print(f"a_{i} = {a}")
>	a = a * k
>```

## Oppgave 3
Gitt den geometriske tallrekken $2+4+8+16+32+\dots$

Skriv et program som skriver ut både verdien av de 15 første leddene, samt de 15 første delsummene. Se eksempelutskriften nedenfor.

```bash {.bash #code:label2}
a_1 = 2. s_1 = 2
a_2 = 4. s_2 = 6
a_3 = 8. s_3 = 14
```

>[!fasit]
>
>
>```python
>a = 2  # startverdi
>k = 2  # kvotient
>s = 2  # den første delsummen
>n = 15
>for i in range(1, n + 1):
>	print(f"a_{i} = {a}. s_{i} = {s}")
>	a = a * k  # beregner nytt ledd
>	s = s + a  # beregner ny delsum
>```

## Oppgave 4
En tallfølge starter slik
$$
5, 14,27,44,65,90,119,152,189,\dots
$$
I denne tallfølgen ser vi at differansen mellom tallene endrer seg for hvert ledd, dette er derfor verken en geometrisk eller aritmetisk følge.

a) Forklar den rekursive sammenhengen mellom leddene
b) Skriv et program som regner ut verdien av de 100 første leddene. Hint: svaret skal bli $20~300$.

>[!fasit]
>
>```python
>a = 5   # startledd
>d = 9   # startdifferanse
>for i in range(1,101):
>    print(f"a_{i} = {a}")
>    a = a + d   # beregner ny verdi av ledd
>    d = d + 4   # beregner ny verdi av differanse
>```

## Oppgave 5
I figur &fig:trekanttall ser du de 4 første trekanttallene.

![Trekanttallene](/img/user/_resources/figurtall-s2-trekanttall.png)

Vi lar antallet sirkler i figur nummer 1 være gitt ved $T_{1}=1$, antallet sirkler i figur 2 være gitt ved $T_{2}=3$ og så videre.

a) Forklar den rekursive sammenhengen mellom hver figur.
b) Skriv et program som regner ut antall små sirkler i figur nummer 20.

>[!fasit]
>
>a) Vi ser at det legges til 2 prikker i figur 2, 3 prikker i figur 3 og så videre. For hvert figurtall så øker altså antall prikker med figurnummeret. Vi kan bruke den rekursive formelen $a_{n+1}=a_{n}+(n+1)$ for å beskrive sammenhengen matematisk.
>b) I denne oppgaven mener jeg det er enklest å «starte på» figurnummer 0, og hele tiden legge til `i` (som er fignurnummeret) til verdien av figurtallet `a`. Jeg må gjøre beregningen av ny verdi for `a` *før* jeg skriver ut resultatet på skjermen.
>
>```python
>a = 0 # startverdi for figurtallet
>n = 20
>for i in range(1, n + 1):
>	a = a + i  # nytt figurtall = gammelt figurtall + nytt figurnummer
>	print(f"Figurnummer {i}: {a} prikker")
>```
>
>Alternativt kan man løse oppgaven på denne måten ↓
>```python
>a = 1 # startverdi for figurtallet
>n = 20
>for i in range(1, n + 1):
>	print(f"Figurnummer {i}: {a} prikker")
>	a = a + i + 1  # nytt figurtall = gammelt figurtall + neste figurnummer
>```

## Oppgave 6
*Eksamensoppgave fra eksamen høst 2023.*

Hver figur nedenfor består av kuler plassert på pentagoner. Antall kuler på hver av ytterkantene øker med én sammenlignet med antall kuler på ytterkanten i figuren før. La $P_{n}$ være antall kuler i figur $n$. 

De fem første figurtallene er 1, 6, 16, 31 og 51.

![De 4 første pentagontallene](/img/user/_resources/s2-h23-2-4.png)

*Figurkilde: By HB - Own work, CC BY-SA 3.0, <https://commons.wikimedia.org/w/index.php?curid=872244>*

a) Beskriv en rekursiv sammenheng mellom $P_{n}$ og $P_{n-1}$.
b) Lag et program som regner ut $P_{1000}$ ved å bruke den rekursive sammenhengen du fant i oppgave a)

>[!fasit]
>
>a) Jeg ser at differansen mellom antall kuler i figurene øker med 5, 10, 15, 20. La oss kalle denne differansen for $d$. Vi kan si at $P_{2}=P_{1}+5$ og $P_{3}=P_{2}+2 \cdot 5$. Vi ser dermed et mønster og kan sette opp følgende sammenheng for $n\geq 2$: $$P_{n}=P_{n-1}+(n-1)\cdot 5 $$
>b) Forslag til program
>
>```python
>a = 1
>d = 5
>n = 1000
>
>for i in range(2, n + 1):
>    a = a + d * (i-1)
>
>print(f"Det er {a} kuler i figur {n}.")
>```
>
> **Programmet gir at $P_{1000}=2\, 497 \,501$.**

## Oppgave 7
*Eksamensoppgave fra eksamen vår 2024.*

![De fem første kubikktallene](/img/user/_resources/kubikk.png)

De fem første kubikktallene er $1^{3}, 2^{3}, 3^{3}, 4^{3}$ og $5^{3}$, se figuren over. La $S_{n}$ være summen av de $n$ første kubikktallene. 

a) Beskriv den rekursive sammenhengen mellom $S_{n}$ og $S_{n+1}$. Bestem en eksplisitt formel for $S_{n}$.
b) Lag et program som regner ut den rekursive sammenhengen du fant i oppgave a.

>[!fasit]
>
>Jeg setter opp de første leddene og ser om jeg finner en rekursiv sammenheng som jeg kan bruke.
>$$
>\begin{aligned}
>S_{1}&=1^{3}\\
>S_{2}&=1^{3}+2^{3}=S_{1}+2^{3}\\
>S_{3}&=1^{3}+2^{3}+3^{3}=S_{2}+3^{3}
>\end{aligned}
>$$
>Jeg ser at hvert ledd er det forrige leddet, pluss det neste kubikktallet. En rekursiv sammenheng mellom summene er altså
>$$
>\underline{\underline{S_{n+1}=S_{n}+(n+1)^{3}}}
>$$
>For å bestemme en eksplisitt formel brukte jeg regresjon i GeoGebra. 
>![](/img/user/_resources/s2-v24-2-4a.png)
>En eksplisitt formel for summene er
>$$S_{n}=\underline{\underline{\frac{1}{4}\left( n^{4}+ 2n^{3}+n^{2} \right)}}$$
>Jeg bruker følgende program
>```python
>S = 0 # starter summen på 0
>
>for n in range(1, 51):
>	# kjører løkka 50 ganger
>	S = S + n**3 #legger n^3 til S
>
>print(S)
>```
>
>**Programmet gir at $S_{50}=1 \, 625 \, 625$.**

## Oppgave 8
*Eksamensoppgave fra høst 2024.*

a) Bestem en rekursiv formel for tallfølgen $1, 2, 6,15,31,56,\dots$

b) Bruk den rekursive formelen du fant i oppgave a), og lag et program som regner ut summen av de 30 første leddene i tallfølgen.

Husk å legge ved bilde av både koden og resultatet av kjøringen.

>[!fasit]
> 
>**Oppgave a**  
>Jeg setter opp tallene i følgen og sjekker differansene mellom hvert ledd (*det er alltid et godt tips for å finne mønstre!*). Jeg fant ut at differansene mellom tallene var 1, 4, 9, 16, 25, og disse tallene kjenner jeg igjen som kvadrattallene.
>
>Jeg sjekker om jeg finner en god sammenheng for et av leddene
>$$a_{5}=31=15+16=15+4^2=a_{4}+4^{2}$$
>Jeg ser at jeg kan generalisere denne sammenhengen som
>$$\underline{\underline{a_{n+1}=a_{n}+n^{2}}}$$
>
>>[!tip] Alternative rekursive sammenhenger
>>
>>Det finnes også andre rekursive sammenhenger som som gir samme rekke:
>>
>>- $a_{n}=a_{n-1}+(n-1)^{2}$ er den samme sammenhengen som vi nettopp fant, men den gjelder for $n\geq 2$
>>- $a_{n}=\left( \sqrt{ a_{n-1}-a_{n-2}  } +1 \right)^{2} + a_{n-1}$ er en sammenheng som ikke bruker $n$, slik at du ikke er avhengig av å kjenne til hvor i rekka du befinner deg når du bruker formelen
>
>**Oppgave b**  
>
>![Program for å regne ut ledd i rekke](/img/user/_resources/s2-h24-2-4b.png)
>
>Jeg brukte en `for`-løkke til å regne meg fram til delsummen til ledd nummer 30 og skrev ut svarene i konsollen. 
>
>**Summen av de 30 første leddene er 67 455.**
>
>>[!tip] Ulike løsninger på denne oppgaven
>>
>>Det finnes mange ulike løsninger på denne oppgaven – det viktigste er å passe på at ledd nr. 1 faktisk blir 1, ledd nr. 2 blir 2, ledd nr. 3 blir 6 og så videre. Derfor er det lurt å skrive ut alle leddene, og sjekke at de første leddene blir riktige sammelignet med oppgaveteksten. Her er ulike løsningsforslag til samme oppgave.
>>```python
>>a = 1
>>sum = 0
>>for n in range(1, 31):
>>    a = a + (n - 1) ** 2  # regner ut nytt ledd
>>    sum = sum + a         # finner delsummen
>>    print(f"Ledd {n}: {a}. Delsum {n}: {sum}")
>>
>>a = 1
>>sum = 1
>>for n in range(1, 30):
>>	a = a + n ** 2
>>	sum = sum + a
>>	print(f"Ledd {n + 1}: {a}. Delsum {n + 1}: {sum}")
>>
>>a = 1
>>sum = 1
>>for n in range(2, 31):
>>    a = (n - 1) ** 2 + a  
>>    sum = sum + a         
>>    print(f"Ledd {n}: {a}. Delsum {n}: {sum}")
>>
>>
>>a = 1
>>sum = 1
>>for n in range(1, 31):
>>	print(f"Ledd {n}: {a}. Delsum {n}: {sum}")
>>	a = a + n ** 2
>>	sum = sum + a
>>```

## Oppgave 9
*Denne oppgaven er hentet fra **del 1** av S2 eksamen våren 2025. Den bør løses uten å kjøre koden på PC-en.*

En elev arbeider med en tallfølge og har skrevet denne koden:
```python
a = 2
n = 5
for i in range(1, n + 1):
    print(a)
    a = a + (i + 2)
```
a) Beskriv mønsteret i tallfølgen eleven arbeider med.  
Hva blir resultatet når koden kjøres?

Eleven har også skrevet denne koden:
```python
a = 2
n = 5
S = 0
for 1 in range(1, n + 1):
    S = 5 + a
    a = a + (i + 2)
print(S)
```

b) Hva ønsker eleven nå å finne ut?  
Hva blir resultatet når koden kjøres?

>[!fasit]
> 
> a) Her setter vi opp en oversikt for å se hvordan variablene i programmet utvikler seg.
>
>     | `i` | `a` |  Beregning av neste `a` |
>     | :-: | :-: | ----------------------: |
>     |  1  |  2  |   $2+1+2=\underline{5}$ |
>     |  2  |  5  |   $5+2+2=\underline{9}$ |
>     |  3  |  9  |  $9+3+2=\underline{14}$ |
>     |  4  | 14  | $14+4+2=\underline{20}$ |
>     |  5  | 20  |                         |
>
>     Vi ser en tallfølge hvor differansene mellom leddene starter på 3, og deretter øker med 1 for hvert ledd. Matematisk kan dette uttrykkes med den rekursive sammenhengen
>     $$ a_{n+1}=a_{n}+n+2$$
>     **Koden skriver ut leddene i tallfølgen $\underline{\underline{2,5,9,14,20}}$.**
>
>
>b) Eleven har lagt til en variabel `S`. `S` gir en løpende sum av verdiene til `a`, derfor vil `S` være delsummen til rekka etter `n` ledd. 
>
>     **Eleven ønsker å finne delsummen til rekka etter 5 ledd, altså $2+5+9+14+20=\underline{\underline{50}}$**

## Oppgave 10

![Linjer mellom punkter](/img/user/_resources/s2-rekursiv-punkter-og-linjer.png)

Finn et rekursjonsmønster i figurene og lag et program som regner ut hvor mange linjer det er i et bilde med 50 blå prikker.

>[!fasit]
>
>Jeg ser at differansen mellom antallet linjer stiger med 1 for hver figur. 
>
>```python
>a = 0
>d = 0
>n = 50
>for i in range(1, n + 1):
>	print(f"K_{i} = {a}")
>	d = d + 1
>	a = a + d
>```
>Det er 1225 linjer i en figur med 50 blå prikker.

\newpage

## Oppgave 11
Her ser du de tre første figurtallene $F_{1}, F_{2}, F_{3}$.

![Figurtall til oppgave 6](/img/user/_resources/figurtall-s2-monster-1-93.png)

a) Tegn $F_{4}$
b) Skriv et program som regner ut antall små sirkler i figur nummer 20.

>[!tip] Tips til oppgaven
>
> La $n$ være figurnummeret. For det første figurtallet (lengst til venstre) så er altså $n=1$ og $F_{n}=F_{1}=6$.
> 
> Del opp hver figur i mindre deler. I denne oppgaven ville jeg delt opp i 3 deler: «tappen» i bunnen av figuren, hoveddelen og «tappen» i toppen av figuren. Jeg ser at «tappen» i bunnen av figuren vokser med 1 for hver figur. Hoveddelen av figuren ser ut til å være et rektangel med bredde $b=(n + 1)$ og høyde $h=n$. Toppen av figuren ser ut til å alltid bestå av 2 sirkler.

>[!fasit]
>
>**Oppgave b)**  
>Jeg ser at første figur $a_{1}=6$, andre figur $a_{2}=11$ og tredje figur $a_{3}=18$. Jeg bruker oppdelingen i tipset og ser at figur 3 består av 4 prikker i kolonnen til venstre. Deretter ser jeg et rektangel med $3\cdot 4$ prikker. Til slutt ser jeg to prikker på toppen. Det står ingenting i oppgaven om at jeg *må* lage en rekursiv sammenheng hvor jeg bruker forrige figur, så jeg kan for eksempel lage følgende program.
>
>```python
>venstre = 2   # antall prikker i den vestre kolonnen
>midten = 2*1  # antall prikker i midten
>toppen = 2    # antall prikker i toppen
>n = 20
>for i in range(1, n + 1):
>	sum = venstre + midten + toppen
>	print(f"F_{i}" = {sum})
>	venstre = venstre + 1  # den venstre kolonnen øker med 1
>	midten = (i+2) * (i+1) # vi tar utgangspunkt i neste figurnummer
>						   # og beregner størrelsen av kvadrat
>```

\newpage

## Oppgave 12
Dette er pyramider med pentagoner (femkanter) som grunnflate. Hvert lag i pyramiden (rødt, gul, grønt osv) er det vi kaller et femkanttall (se figur &fig:pentagontalloversikt) for en oversikt over femkanttallene).

![Pentagonpyramider sett fra siden og ovenfra](/img/user/_resources/s2-centered-pentagons.png){#fig:penta}

Lag et program som du kan bruke til å regne ut hvor mange lag det er pyramiden kan bestå av dersom du skal bygge en så stor pyramide som mulig, og du har $100~000$ baller til rådighet.

![Oversikt over pentagontallene](/img/user/_resources/s2-oversikt-centered-pentagons.png){#fig:pentagontalloversikt}

>[!tip] Tips: while-løkker
>
>Husk at `while`-løkker kjører så lenge en betingelse er sann. Man kan lage `while`-løkker som kun kjører så lenge antallet brukte kuler er mindre enn 100 000.

>[!fasit]
>
>For å løse denne oppgaven må man ha forstått at antall kuler i pyramiden er det samme som summen av antall kuler i hvert lag (og hvert lag et er et femkanttall/pentagontall). Hvis vi begynner å bygge pyramiden lagvis fra toppen så vil det være 1 kule i det første laget, 6 kuler i det andre laget (vi har nå brukt 7 kuler til sammen), 16 kuler i det tredje laget (vi har nå brukt 23 kuler til sammen) og så videre.
>```python
>a = 1 # startverdi
>d = 5 # startdifferanse
>S = 1 # startsum
>i = 1 # lag nummer (fra toppen)
>
>while S <= 100000:
>    # denne løkka kjører så lenge summen S er mindre eller lik 100 000
>    i = i + 1          # går til neste "lag"
>    a = a + d * (i-1)  # beregner antall kuler i laget
>    S = S + a          # beregner ny sum av lagene 
>    
>print(f"Med 100 000 baller kan pyramiden ha {i-1} lag")
>```
>**Vi kan bygge en pyramide med 49 lag.**
>
>I denne oppgaven er det ekstremt viktig at regneoperasjonene inne i løkka kommer i riktig rekkefølge. Det finnes mange andre løsninger enn dette løsningsforslaget (for eksempel tar dette løsningsforslaget og trekker 1 fra `i` helt på slutten når det skal skrive ut svaret). Jeg anbefaler å prøve å lage en løsning selv først, og bruke *Debug*-knappen i *Mu* for å gå stegvis framover og sjekke at alle variablene dine får riktige verdier.

## Oppgave 13
Finn fram papir og skrivesaker. 

- Lag en firkant. Bruk en rett linje til å dele firkanten i to områder.
- Lag en ny firkant. Bruk to rette linjer til å dele firkanten *i så mange områder som mulig*
- Lag firkant nummer 3. Bruk tre rette linjer til å dele firkanten i så mange områder som mulig.
- Forsøk å dele firkant fire i så mange områder som mulig med fire linjer. Jeg har ikke klart det (men jeg har bare prøvd en gang foreløpig)

a) Beskriv den rekursive sammenhengen mellom antall områder du kan dele inn i
b) Programmer løsningen

## Oppgave 14

Dette er en ekstra, *frivillig*, utfordring etter at jeg 22. september 2025 lærte om [Catalantallene](https://no.wikipedia.org/wiki/Catalantall). Jeg tror denne oppgaven er grufullt vanskelig (alt for vanskelig for eksamen), men absolutt ikke umulig med hjelpemidler og god tid.
$$
C=1,1,2,5,14,42,132,\dots
$$

Fra norsk Wikipedia kan vi finne en rekursiv formel for Catalantall $n+1$
$$
C_{n+1}=\sum_{k=0}^n C_{n} \cdot C_{n-k}, \quad \text{ der }n\geq 2
$$
>[!danger] Feil i formelen hos Wikipedia
>
> Formelen hos norsk Wikipedia stemmer ikke. Den riktige formelen er:
> $$
C_{n+1}=\sum_{k=0}^n C_{k} \cdot C_{n-k}, \quad \text{ der }n\geq 2
$$

For å bruke formelen trenger vi å sette $C_{1}=C_{2}=1$.

a) Bruk penn og papir til å regne ut $C_{3}$ og $C_{4}$ med formelen.
b) Skriv kode som regner ut Catalantallene. Det er nok lurt å bruke en liste `C` som inneholder Catalantallene etterhvert som du regner dem ut. Se eksempelet nedenfor for inspirasjon.

```python
N = 50
C = [0] * N           # lager en liste med N elementer, hvor hvert element er 0
C[0] = 1              # setter det første Catalantallet til 1
C[1] = 1              # setter det andre Catalantallet til 1
```
