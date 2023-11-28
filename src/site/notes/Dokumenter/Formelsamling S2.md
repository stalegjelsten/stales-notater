---
{"dg-publish":true,"permalink":"/Dokumenter/Formelsamling S2/","title":"Formelark S2","tags":["s2"]}
---


## Følger, rekker og lån
En tallfølge er en ordnet liste med tall: $a_{1}, a_{2}, a_{3}, a_{4}, \dots, a_{n}$

En rekke er summen av tallene i en tallfølge. Delsummen $s_{n}$ av de $n$ første leddene i en følge er gitt ved
$$
\sum_{i=1}^n a_{i}=a_{1}+ a_{2}+a_{3}+a_{4}+\dots+a_{n}
$$

| Forklaring                           | Formel                                   |
| ------------------------------------ | ---------------------------------------- |
| Ledd i aritmetisk følge (rekursiv)   | $a_{n + 1} = a_{n} + d$               |
| Ledd i aritmetisk følge (eksplisitt) | $a_{n} = a_{1} + (n-1)\cdot d$        |
| Ledd i geometrisk følge (rekursiv)   | $a_{n + 1} = a_{n} \cdot k$           |
| Ledd i geometrisk følge (eksplisitt) | $a_{n} = a_{1} \cdot k^{n-1}$          |
| Aritmetisk rekke (sum av følge)      | $s_{n}=\frac{a_{1}+a_{n}}{2}\cdot n$   |
| Geometrisk rekke (sum av følge)      | $s_{n}=a_{1}\cdot \frac{k^{n}-1}{k-1}$ |
| Uendelig geometrisk rekke            | $-1<k<1 \implies s=\frac{a_{1}}{1-k}$   |

### Rekker og konvergens
Ei rekke konvergerer og har summen $s$ dersom summen $s_{n}$ av $n$ første leddene nærmer seg tallet $s$ når $n \to \infty$. Altså
$$\lim_{n \to \infty}{s_{n} = s}$$
Geometriske rekker er alltid konvergente når $k \in \left\langle - 1\ ,\ 1 \right\rangle \iff -1<k<1$. Summen av denne typer rekker er gitt ved formelen
$$
s=\frac{a_{1}}{k-1}
$$

### Programmering av følger og rekker
Ifølge læreplanen skal dere utforske *rekursive sammenhenger* med programmering. En rekursiv sammenheng vil si at vi alltid bruker ett ledd til å regne ut det neste leddet – for å regne ut $a_{n+1}$ så trenger vi først å ha regnet ut $a_{n}$.

#### Ledd i aritmetisk tallfølge
```python
# Regner ut de første leddene i en aritmetisk tallfølge
# med a_0 = 0 og d = 2.
a = 0 
d = 2
antall_ledd = 10
for i in range(1, antall_ledd + 1):
	print(f"a_{i} = {a}")
	a = a + d
```

Ved bruk av `print(f"")` så kan vi blande tekst og variabler. Variablene skriver vi slik `{variabelnavn}`.

#### Delsum av geometrisk rekke
```python
# Regner ut de første leddene og delsummene i
# geoemtrisk rekke med a_0 = 1 og k = 1.5
a = 1 
k = 1.5
delsum = a
antall_ledd = 10
for i in range(1, antall_ledd + 1):
	print(f"a_{i} = {a:.2f}. s_{i} = {delsum:.2f}")
	a = a * k
	delsum = delsum + a
```

Her bruker vi en teller, `delsum`, som i hver omgang av `for`-løkka blir oppdatert med den nye summen.

Vi kan avrunde desimaltall med `{variabelnavn:.2f}` der 2-tallet er antallet desimaler vi ønsker.

#### Eksempel med følge som ikke er geometrisk eller aritmetisk

> **Oppgavetekst**: Gitt følgende tallfølge: $1, 3, 4, 8, 15, 27, 50, …$. De 3 første leddene i denne følgen er spesielle. Deretter følger tallene et fast mønster.
>
>Lag et program som skriver ut de første n leddene i denne følgen. Hvis programmet ditt fungerer riktig vil du få $a_{50}  = 11986911799691$.

Etter å ha funnet ut at $a_{4}=a_{1}+a_{2}+a_{3}$ og $a_{5}=a_{4}+a_{3}+a_{2}$ så kan vi tenke oss fram til at mønsteret i følgen er 
$$
a_{n} = a_{n-1} + a_{n-2} + a_{n-3},\quad n \geq 4
$$
Vi kan programmere dette på følgende måte

```python
a_minus3 = 1
a_minus2 = 3
a_minus1 = 4
n = 50

for i in range(4, n + 1):
  a_i = a_minus3 + a_minus2 + a_minus1
  print(f"a_{i} = {a_i}")
  a_minus3 = a_minus2
  a_minus2 = a_minus1
  a_minus1 = a_i
```

Her oppdaterer vi hele tiden verdiene av de tre foregående leddene.

Vi kan også løse den samme oppgaven ved bruk av lister. Her bruker vi metoden `append` på lista `a`. Dette legger til et nytt element i slutten av lista. Dette nye elementet skal være lik summen av de tre foregående leddene[^1].

```python
a = [1, 3, 4]
antall_ledd = 50
for i in range(4, antall_ledd+1):
  a.append(a[i-2] + a[i-3] + a[i-4])
print(a)
```

### Nåverdi og lån
#### Nåverdi
Nåverdi forteller oss hvor mye et fremtidig (eller fortidig) beløp er verdt i nåtidens penger. Det er vanlig at penger blir mindre og mindre verdt for hvert år siden vi forventer avkastning på investeringene våre.

Nåverdien $N$ til et fremtidig beløp $B$ er gitt ved 
$$
N=\frac{B}{v^{n}}
$$

Der $v$ er vekstfaktoren til kalkulasjonsrenta og $n$ er antall perioder. Hvis du vil finne nåverdien til et beløp bakover i tid så velger du en negativ verdi for $n$.

#### Serielån
Alle avdragene er like store, men rentene minker og derfor minker også terminbeløpene. Nåverdiene av terminebeløpene danner en aritmetisk rekke.

Vi finner avdragene med
$$
\text{avdrag}=\frac{\text{lånebeløp}}{\text{antall terminer}}
$$
Vi finner terminbeløpene med
$$
\text{terminbeløp} = \text{avdrag} + \text{rente av restlånet}
$$

#### Annuitetslån
Alle terminebeløpene er like store. Rentene synker i løpet av nedbetalingsperioden og avdragene øker. Nåverdiene av terminbeløpene danner en geometrisk rekke slik at 

$$
L = \sum_{i=1}^n \frac{T}{v^{i}}
$$

Lånebeløpet $L$ er terminfaktoren $F$ multiplisert med terminbeløpet $T$.
$$L = F \cdot T$$
Vi finner terminfaktoren ved hjelp av følgende formel hvor $v$ er vekstfaktoren til renta per termin og $n$ er antall terminer
$$F = \frac{1 - \frac{1}{v^{n}}}{v - 1}$$

## Logaritmer
### Egenskaper ved logaritmefunksjoner
En logaritmefunksjon er den inverse funksjonen til en eksponentialfunksjon.

- Eksponentialfunksjonen $f(x)=10^{x}$ har tilhørende logaritmefunksjon $\log_{10}x$ eller ofte bare kalt $\log x=\lg x$.
- Eksponentialfunksjonen $f(x)=e^{x}$ har tilhørende logaritmefunksjon $\ln x$
- Eksponentialfunksjonen $f(x)=a^{x}$ har tilhørende logaritmefunksjon $\log_{a}x$ for $a>0$ (det finnes altså uendelig mange typer eksponentialfunksjoner og logaritmefunksjoner)

Dette betyr at $\ln e^{x}=x$ og $\log_{10}10^{x}=x$.

Logaritmefunksjonene er definert for alle positive tall slik at definisjonsmengden blir $D_{f}=\langle 0 , \infty\rangle$.

Vi bruker ofte $\ln x$ i S2 siden denne er enklere å derivere og integrere enn $\log x$.

### Regneregler for logaritmer
Her bruker jeg $\ln$ som logaritme, men disse reglene gjelder for *alle* typer logaritmer.

| Forklaring                 | Formel                           |
| -------------------------- | -------------------------------- |
| Bruke logaritme på likning | $a=b \iff \ln a=\ln b$         |
| Hente ned eksponent        | $\ln a^{x}=x\ln a$             |
| Logaritme til produkt      | $\ln (a\cdot b)=\ln a +\ln b$ |
| Logaritme til kvotient     | $\ln \frac{a}{b}=\ln a-\ln b$ |
| Nullpunkt til logaritmer   | $\ln 1=0$                                 |

Merk at den siste regelen forteller oss hvor logaritmefunksjonene har sitt eneste nullpunkt. For $f(x)=\ln x$ vil funksjonen være negativ for $0<x<1$ og positiv for alle $x>1$.

## Derivasjon
Definisjon: Hvis $f(x)$ er kontinuerlig i et punkt $x$ så er den deriverte i punktet:

$$f'(x) = \lim_{\Delta x \to 0}\frac{f(x + \Delta x) - f(x)}{\Delta x}$$

Den deriverte i et punkt er lik den momentane vekstfarten i punktet og dermed også lik stigningstallet til tangenten til $f$ i punktet.

| Forklaring        |        Funksjon        |               Derivert                |
| ----------------- |:----------------------:|:-------------------------------------:|
| Konstant funksjon |          $k$           |                  $0$                  |
| Potensfunksjon    |        $x^{r}$         |          $r \cdot x^{r - 1}$          |
| Konstante koeff.  |     $k \cdot g(x)$     |            $k \cdot g'(x)$            |
| Summer            |    $g(x) \pm h(x)$     |           $g'(x) \pm h'(x)$           |
| Produkt           |   $u(x) \cdot v(x)$    | $u'(x) \cdot v(x) + u(x) \cdot v'(x)$ |
| Kvotienter        |  $\frac{u(x)}{v(x)}$   |       $\frac{u'v - uv'}{v^{2}}$       |
| Eksponentialfunk  |        $e^{x}$         |                $e^{x}$                |
| Eksponentialfunk  |        $a^{x}$         |             $a^{x}\ln x$              |
| Logaritme         |        $\ln x$         |             $\frac{1}{x}$             |
| Kjerneregelen     | $g\left( u(x) \right)$ |          $g'(u) \cdot u'(x)$          |

Huskeregel kjerneregelen: Multipliser den deriverte av den ytre funksjonen med den deriverte av kjernen.

### Den deriverte av ln x
$$
\big( \ln (x) \big) '=\frac{1}{x}
$$

Merk at selv om $g(x)=\frac{1}{x}$ er definert for $x\in \mathbb{R} \setminus 0$ så er den deriverte av logaritmefunksjonen kun definert for $x>0$. 

Funksjonen $f(x)=\ln x$ har definisjonsmengde $D_{f} = \langle 0, \to \rangle$. Derfor kan ikke den deriverte ha noe *større* definisjonsmengde enn dette. For å derivere en funksjon så den være kontinuerlig i punktet. Det gir ikke mening å snakke om vekstfarten til $f$ i $x=-2$ siden $f(-2)$ ikke eksisterer.

## Økonomi
Her lar vi $I(x)$ være inntektene ved salg av $x$ enheter og $K(x)$ være produksjonskostnadene ved produksjon av $x$ enheter. Overskuddet $O(x)$ er da gitt ved
$$
O(x)=I(x)-K(x)
$$

### Grenseinntekt og grensekostnad
Grenseinntekten $I'(x)$ er den deriverte av inntektsfunksjonen. Grenseinntekten $I'(x)$ forteller oss omtrent hvor mye vi tjener på å selge én mer enhet.

Grensekostnaden $K'(x)$ er den deriverte av kostnadsfunksjonen. Grensekostnaden $K'(x)$ forteller oss omtrent hvor mye det koster å produsere én mer enhet.

### Maksimalt overskudd
Vi har maksimalt overskudd når grenseinntekt er lik grensekostnad fordi
$$
\begin{aligned}
O'(x) &=0 \\
I'(x)-K'(x) &= 0\\
I'(x) &= K'(x)
\end{aligned}
$$

Hvis du får flere løsninger så bør du sjekke hvilken løsning som er et toppunkt.

### Enhetskostnader
Enhetskostnaden $E(x)$ fordeler produksjonskostnadene $K(x)$ på antall enheter $x$. Vi finner altså ut hva det koster å produsere 1 enhet ved vår nåværende produksjonsmengde.

$$
E(x)=\frac{K(x)}{x}
$$

Vi kan finne de laveste enhetskostnadene på to måter, enten ved å løse $E'(x)=0$ eller ved å løse $K'(x)=E(x)$. Utledningen for den siste formelen er som følger

$$
\begin{aligned}
E(x)&=\frac{K(x)}{x}\\
E'(x)&=\frac{K'(x)\cdot x-K(x)\cdot1}{x^{2}}\\
\end{aligned}
$$

Vi setter uttrykket til den deriverte lik siden vi leter etter punkter hvor $E'(x)=0$.
$$
\begin{aligned}
\frac{K'(x)\cdot x-K(x)\cdot1}{x^{2}}&=0\\
K'(x)\cdot x-K(x)\cdot1&=0\\
K'(x)\cdot x-K(x)&=0\\
K'(x)\cdot x &= K(x)\\
K'(x)&= \frac{K(x)}{x}\\
K'(x)&= E(x)\\
\end{aligned}
$$

Vi kan også løse den siste likningen grafisk. Tegn først grafen til kostnadsfunksjonen $K(x)$. Dersom grensekostnadene skal være lik enhetskostnadene så kan vi finne ut hvilken rett linje som går gjennom origo (slik alle linjer som skal finne enhetskostnader gjør) og samtidig er tangent til kostnadsfunksjonen $K$. 


### Etterspørsel

> **Kommentar fra Ståle**: Dette er pensum fra S1 i vårt læreverk. Andre læreverk lærer dette i S2. Jeg tror ikke det er relevant for eksamen, men jeg legger det ved her for sikkerhets skyld.

Etterspørselen $q$ er en funksjon av prisen $p$ slik at $q(p)$. Etterspørselen er også lik antall solgte enheter $x$ slik at
$$
x=q(p)
$$

Inntektene er $\text{pris} \times \text{antall solgte}$ eller $I(x)=p \cdot x$. Hvis vi bytter ut $x$ med $q(p)$ så får vi $I(p)=p\cdot q(p)$

På samme måte kan vi vise at kostnadene blir $K(x)=K(q(p))$.


[^1]: Merk at `python`-lister begynner på indeks 0. Det vil si at for å hente ut det første elementet i ei liste som heter `min_liste` så skriver vi `min_liste[0]`. For å hente du det fjerde elementet i lista skriver vi `min_liste[3]`.

## Innledning
> Algebra er vanskelig, men så lenge du ikke gjør noe ulovlig så går det som oftest greit.

I T-, R- og S-matte på videregående så er du nødt til å være god i algebra for å få vist kompetansen din på del 1. I dette notatet har jeg samlet noen vanlige feil som jeg ser at mange elever gjør.

## Forkorting av brøker med bokstavuttrykk
Dere vil ofte komme over brøker som denne
$$
	\frac{2x(x+2)-1}{(x+2)^{2}}
$$
Som flinke og flittige elever så ønsker man gjerne å skrive dette uttrykket så enkelt som mulig. Det er da naturlig å tenke at man kan forkorte bort $(x+2)$ fra teller og nevner på denne måten

>[!danger] Eksempel på feil måte å forkorte brøk med bokstavuttrykk
>
>$$
\frac{2x\cancel{ (x+2) }-1}{(x+2)^{\cancel{ 2 }}}
$$

**Det er ikke lov siden telleren vår består av flere ledd**. Legg merke til at telleren har to ledd i dette tilfellet:

- $2x(x+2)$
- $-1$. 

### Løsning: forkorting av brøker med bokstavuttrykk
Du har alltid lov til å forkorte dersom du faktoriserer teller og nevner først. Det er egentlig akkurat det samme som du gjør når du forkorter brøker med tall. Se hvordan jeg forkorter $\frac{14}{6}$ i dette talleksempelet $\downarrow$
$$
\frac{14}{6}=\frac{2\cdot 7}{2 \cdot 3} = \frac{\cancel{ 2 } \cdot 7}{\cancel{ 2 }\cdot 3}=\frac{7}{3}
$$

Tenk at forkorting av bokstavuttrykk er det samme som forkorting av vanlige brøker: du har kun lov til å forkorte dersom du har samme faktor i teller og nevner, og dersom du har flere ledd i teller eller nevner så må du faktorisere alle leddene.

La oss se på et eksempel med bokstavuttrykk $\downarrow$
$$
\frac{2x^{2} +3x}{4x-x^{2}}=\frac{x(2x + 3)}{x(4-x)}=\frac{\cancel{ x }(2x+3)}{\cancel{ x }(4-x)}=\frac{2x+3}{4-x}
$$

Her fant jeg faktoren $x$ i hvert av de fire leddene (to ledd i teller og to i nevner). Jeg faktoriserte derfor ut $x$ og deretter kan jeg forkorte $x$. Til slutt står vi igjen med leddene $2x$, $3$, $4$ og $-x$. Disse har ingen felles faktorer, og det gir ikke mening å faktorisere videre.

>[!important] Forkorting av brøker med bokstavuttrykk
>
>Se etter felles faktorer i **alle** ledd i teller og nevner. Felles faktorer kan alltid forkortes, men det er ofte lurt å faktorisere teller og nevner først for å unngå å gjøre feil.


## Å løse opp parentes med eksponent
Vi får ofte uttrykk som $(x+2)^{2}$ eller $(2x^{2}-4x)^{3}$ hvor vi har en parentes med flere ledd opphøyd i et tall. Det er da fristende å sette inn eksponenten på hvert av leddene i parentesen på denne måten 

>[!danger] Eksempel på feil måte å løse parentes med eksponent
>
>$$
(x+2)^{2}=x^{2}+2^{2}=x^{2}+4
$$

**Dette er ikke lov**. Husk at 
$$(x+2)^{2}=(x+2)\cdot (x+2) = x^{2}+4x+4$$

>[!tip] Kvadratsetningene
>
>Vi bruker ofte kvadratsetningene når vi har uttrykk opphøyd i andre.
>
> - Første kvadratsetning: $(a+b)^{2}=a^{2}+2ab+b^{2}$
> - Andre kvadratsetning: $(a-b)^{2}=a^{2}-2ab+b^{2}$
> - Tredje kvadratsetning (konjugatsetningen): $a^{2}-b^{2}=(a+b)(a-b)$

### Løsning: løse opp parentes med eksponent
Før du prøver å løse opp parentesen bør du spørre deg selv om det er *nødvendig* å gange den ut. For eksempel er uttrykket $(x+2)^{2}$ allerede et flott faktorisert uttrykk. 

Hvis det er nødvendig å løse opp parentesen må du sjekke om den inneholder flere ledd. Dersom det kun er ett ledd inne i parentesen kan du bruke potensregelen $(a \cdot b)^{m}=a^{m} \cdot b^{m}$ på denne måten $\downarrow$

$$
(3ax)^{2}=3^{2}\cdot a^{2} \cdot x^{2}=9a^{2}x^{2}
$$
Hvis parentesen din inneholder flere ledd så kan det være du er nødt til å regne en del. Er parentesen opphøyd i 2 så kan du bruke kvadratsetningene, er den opphøyd i mer enn 2 så må du multiplisere sammen alle leddene.

La oss se hvordan vi kan regne ut $(5x+3)^{3}$

$$
\begin{aligned}
(5x+3)^{3} \\
(5x+3)(5x+3)(5x+3)\\
\big((5x \cdot 5x)+(5x \cdot 3 )+ (3 \cdot 5x) + (3\cdot 3)\big)(5x+3)\\
\big(25x^2+15x+15x + 9\big)(5x+3)\\
\big(25x^2+30x + 9\big)(5x+3)\\
(25x^{2}\cdot 5x)+(30x \cdot  5x)+(9\cdot 5x)+(25x^{2}\cdot 3)+(30x \cdot 3)+(9\cdot 3)\\
125x^{3}+150x^{2}+45x+75x^{2}+90x+27\\
125x^{3}+225x^{2}+135x+27
\end{aligned}
$$

Som dere ser er dette utrolig arbeidskrevende (det finnes noen triks for å gjøre dette enklere med bruk av [[Pascals trekant\|Pascals trekant]]), men det er likevel ikke noe jeg tror dere noen gang trenger å gjøre i løpet av videregående. Hvis dere har eksponenten 3 eller høyere så ville jeg derfor ikke løst opp parentesen.

>[!tip] Løse opp parentes med eksponent
>
> 1. Vurder først om du trenger å løse opp parentesen. Ofte er det ikke nødvendig. 
> 2. Hvis du kun har ett ledd inne i parentesen så bruker du potensregelen $(a \cdot b)^{m}=a^{m} \cdot b^{m}$ 
> 3. Hvis du har en parentes med to ledd opphøyd i andre bruker du kvadratsetning
> 4. Har du mer enn to ledd eller opphøyd i mer enn 2 så er det lite sannsynlig at du skal regne dette ut i en skoleoppgave. 
