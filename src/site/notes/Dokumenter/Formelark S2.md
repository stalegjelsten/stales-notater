---
{"dg-publish":true,"permalink":"/Dokumenter/Formelark S2/","title":"Formelark S2","tags":["s2"]}
---


## Følger, rekker og lån

### Følger og rekker
En tallfølge er en ordnet liste med tall: $a_{1}, a_{2}, a_{3}, a_{4}, \dots, a_{n}$

En rekke er summen av tallene i en tallfølge. Delsummen $s_{n}$ av de $n$ første leddene i en følge er gitt ved
$$
s_{n}=\sum_{i=1}^n a_{i}=a_{1}+ a_{2}+a_{3}+a_{4}+\dots+a_{n}
$$

| Forklaring                           | Formel                                   |
| :------------------------------------ | :---------------------------------------- |
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
En enkel tommelfingerregel for å sjekke om en rekke konvergerer er å sjekke om leddene går mot 0 når $n\to \infty$. Dersom rekka ikke konvergerer, så *divergerer* den.

**Geometriske rekker** er alltid konvergente når $k \in \left\langle - 1\ ,\ 1 \right\rangle \iff -1<k<1$. Summen av denne typer rekker er gitt ved formelen
$$
s=\frac{a_{1}}{k-1}
$$

### Programmering av følger og rekker
Ifølge læreplanen skal dere utforske *rekursive sammenhenger* med programmering. En rekursiv sammenheng vil si at vi bruker ett ledd til å regne ut det neste leddet – for å regne ut $a_{n+1}$ så trenger vi først å ha regnet ut $a_{n}$.

#### Ledd i aritmetisk tallfølge
```python
# Regner ut de første leddene i en aritmetisk tallfølge
# med a_0 = 0 og d = 2.
a = 0 
d = 2
n = 10
for i in range(1, n + 1):
	print(f"a_{i} = {a}")
	a = a + d
```

Ved bruk av `print(f"")` så kan vi blande tekst og variabler. Variablene skriver vi med krøllparenteser slik: `{variabelnavn}`.

#### Delsum av geometrisk rekke
```python
# Regner ut de første leddene og delsummene i
# geoemtrisk rekke med a_0 = 1 og k = 1.5
a = 1 
k = 1.5
delsum = a
n = 10
for i in range(1, n + 1):
	print(f"a_{i} = {a:.2f}. s_{i} = {delsum:.2f}")
	a = a * k
	delsum = delsum + a
```

Her bruker vi en teller, `delsum`, som i hver omgang av `for`-løkka blir oppdatert med den nye summen.

Vi kan avrunde desimaltall med `{variabelnavn:.2f}` der 2-tallet er antallet desimaler vi ønsker.

#### Eksempel med følge som ikke er geometrisk eller aritmetisk

> **Oppgavetekst**: Gitt følgende tallfølge: $1, 3, 4, 8, 15, 27, 50, …$
> 
> De 3 første leddene i denne følgen er spesielle. Deretter følger tallene et fast mønster.
>
> Lag et program som skriver ut de første n leddene i denne følgen. Hvis programmet ditt fungerer riktig vil du få $a_{50}  = 11986911799691$.

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

Vi kan også løse den samme oppgaven ved bruk av lister. Her bruker vi metoden `append` på lista `a`. Dette legger til et nytt element i slutten av lista. Dette nye elementet skal være lik summen av de tre foregående leddene.[^1]

```python
a = [1, 3, 4]
antall_ledd = 50
for i in range(4, antall_ledd+1):
  a.append(a[i-2] + a[i-3] + a[i-4])
print(a)
```

### Nåverdi og lån

#### Ordliste

| Begrep         | Forklaring                                              |
| -------------- | ------------------------------------------------------- |
| Rentefot/-sats | Hvor mange prosent rente vi må betale per år (pro anno) |
| Terminer       | Antall innbetalinger                                    |
| Lånebeløp      | Størrelsen på lånet da du tok det opp                   |
| Restlån        | Størrelsen på lånet i dag                               |
| Terminbeløp    | Hvor mye penger du betaler i hver termin                |
| Renter         | Den delen av terminbeløpet som dekker rentene           |
| Avdrag         | Den delen av terminbeløpet som betaler ned på lånet     |
| Termingebyr    | Bankens gebyr for å sende ut faktura                    | 

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
Alle terminebeløpene er like store. Rentene synker i løpet av nedbetalingsperioden og avdragene øker. Lånebeløpet $L$ skal være lik summen av nåverdiene av terminbeløpene:
$$
L = \sum_{i=1}^n \frac{T}{v^{i}}
$$
Legg merke til at dette er en geometrisk rekke med $k=\frac{1}{v}$. Mange oppgaver med annuitetslån på del 2 kan løses ved å sette opp likningen over i CAS.

Vi kan også bruke formler til å regne ut terminbeløpene eller lånebeløpet til et annuitetslån. Lånebeløpet $L$ er terminfaktoren $F$ multiplisert med terminbeløpet $T$.
$$L = F \cdot T$$
Vi finner terminfaktoren ved hjelp av følgende formel hvor $v$ er vekstfaktoren til renta per termin og $n$ er antall terminer
$$F = \frac{1 - \frac{1}{v^{n}}}{v - 1}$$

## Funksjonsdrøfting
Funksjonsdrøfting handler om å finne ut hvordan funksjoner ser ut når du tegner dem. 

- Nullpunkter finner du ved å sette $f(x)=0$
- Topp-, bunn- og terrassepunkter finner du ved å sette $f'(x)=0$
- Vendepunkter finner du ved å sette $f''(x)=0$
- Monotoniegenskaper (når funksjonen vokser og synker) finner du ved å sjekke når $f'(x)>0$ og $f'(x)<0$. Du trenger å faktorisere og tegne fortegnslinje for å finne ut av dette.
- Krumning finner du ved å sjekke når $f''(x)>0$ og $f''(x)<0$. Du trenger å faktorisere og tegne fortegnslinje for å finne ut av dette.

### Logaritmer
#### Egenskaper ved logaritmefunksjoner
En logaritmefunksjon er den inverse funksjonen til en eksponentialfunksjon.

- Eksponentialfunksjonen $f(x)=10^{x}$ har tilhørende logaritmefunksjon $\log_{10}x$ eller ofte bare kalt $\log x=\lg x$.
- Eksponentialfunksjonen $f(x)=e^{x}$ har tilhørende logaritmefunksjon $\ln x$
- Eksponentialfunksjonen $f(x)=a^{x}$ har tilhørende logaritmefunksjon $\log_{a}x$ for $a>0$. Du kan altså velge hvilket som helst positivt tall $a$ som base i logaritmefunksjonen.

Siden logaritmefunksjonen og eksponentialfunksjonene er inverse så vil disse nulle hverandre ut:
$$
\begin{aligned}
\ln e^{x}=x &\iff e^{\ln x}=x\\
\log10^{x}=x &\iff 10^{\log x}=x\\
\log_{a}a^{x}=x & \iff a^{\log_{a} x}=x
\end{aligned}
$$
Logaritmefunksjonene er definert for alle positive tall slik at definisjonsmengden blir $D_{f}=\langle 0 , \infty\rangle$.

Vi velger som oftest den naturlige logaritmen, $\ln x$, i S2 siden denne er enklere å derivere og integrere enn de andre logaritmene.

#### Regneregler for logaritmer
Her bruker jeg den naturlige logaritmen som eksempel, men disse reglene gjelder for *alle* typer logaritmer.

| Forklaring                 |            Formel             |
| :-------------------------- |:-----------------------------:|
| Bruke logaritme på likning |    $a=b \iff \ln a=\ln b$     |
| Hente ned eksponent        |      $\ln a^{x}=x\ln a$       |
| Logaritme til produkt      | $\ln (a\cdot b)=\ln a +\ln b$ |
| Logaritme til kvotient     | $\ln \frac{a}{b}=\ln a-\ln b$ |
| Nullpunkt til logaritmer   |           $\ln 1=0$           |

Merk at den siste regelen forteller oss at alle typer logaritmefunksjonene har sitt eneste nullpunkt i $x=1$. For $f(x)=\ln x$ vil funksjonen være negativ for $0<x<1$ og positiv for alle $x>1$.

### Rasjonale funksjoner
En rasjonal funksjon består av en brøk med polynomfunksjoner i teller og nevner:
$$
f(x)=\frac{P(x)}{Q(x)}
$$

Rasjonale funksjoner har følgende egenskaper:

- Nullpunkt når telleren $P(x)=0$
- Bruddpunkt når nevneren $Q(x)=0$
- Definisjonsmengde er alle $x$ bortsett fra bruddpunktet: $D_{f}=\mathbb{R} \setminus x_{\text{bruddpunkt}}$

#### Asymptoter
Asymptoter er tenkte linjer som en funksjon nærmer seg. Asymptoter kan være horisontale, vertikale eller skrå.

- Vi får vertikale asymptoter i bruddpunktene. Vi finner disse ved å løse $Q(x)=0$.
- Vi får en horisontal asymptote dersom $P$ og $Q$ har samme grad. Vi finner disse ved å dividere leddene i $P$ og $Q$ med høyest grad på hverandre.
- Vi får skrå asymptoter når graden av $P$ er én større enn graden av $Q$. Vi finner denne ved å beregne $P(x):Q(x)$ med polynomdivisjon. Den skrå asymptoten er svaret på divisjonen når du ser bort fra resten.

## Derivasjon
Definisjon: Hvis $f(x)$ er kontinuerlig i et punkt $x$ så er den deriverte i punktet:
$$f'(x) = \lim_{\Delta x \to 0}\frac{f(x + \Delta x) - f(x)}{\Delta x}$$
Den deriverte i et punkt er lik den momentane vekstfarten i punktet og dermed også lik stigningstallet til tangenten til $f$ i punktet.

| Forklaring       |        Funksjon        |               Derivert                |
|:---------------- |:----------------------:|:-------------------------------------:|
| Konstant         |          $k$           |                  $0$                  |
| Potensfunksjon   |        $x^{r}$         |          $r \cdot x^{r - 1}$          |
| Konstante koeff. |     $k \cdot g(x)$     |            $k \cdot g'(x)$            |
| Summer           |    $g(x) \pm h(x)$     |           $g'(x) \pm h'(x)$           |
| Produkt          |   $u(x) \cdot v(x)$    | $u'(x) \cdot v(x) + u(x) \cdot v'(x)$ |
| Kvotienter       |  $\frac{u(x)}{v(x)}$   |       $\frac{u'v - uv'}{v^{2}}$       |
| Eksponentialfunk |        $e^{x}$         |                $e^{x}$                |
| Eksponentialfunk |        $a^{x}$         |             $a^{x}\ln x$              |
| Logaritme        |        $\ln x$         |             $\frac{1}{x}$             |
| Kjerneregelen    | $g\left( u(x) \right)$ |          $g'(u) \cdot u'(x)$          |

Huskeregel kjerneregelen: Multipliser den deriverte av den ytre funksjonen med den deriverte av kjernen.

### Den deriverte av ln x
$$
\big( \ln (x) \big) '=\frac{1}{x}
$$
Merk at selv om $g(x)=\frac{1}{x}$ er definert for $x\in \mathbb{R} \setminus 0$ så er den deriverte av logaritmefunksjonen kun definert for $x>0$. 

Funksjonen $f(x)=\ln x$ har definisjonsmengde $D_{f} = \langle 0, \to \rangle$. Derfor kan ikke den deriverte ha noe *større* definisjonsmengde enn dette. For å derivere en funksjon så den være kontinuerlig i punktet. Det gir ikke mening å snakke om vekstfarten til $f$ i $x=-2$ siden $f(-2)$ ikke eksisterer.

### Stigningstall og tangenter
Stigningstallet, $a$, til tangenten til $f(x)$ i punktet $x=x_{1}$ er lik den deriverte i punktet, $f'(x_{1})$. For å finne likningen til tangenten kan vi sette inn kjente tall i likningen for rett linje
$$
y=ax+b
$$
Vi kan også bruke ettpunktsformelen
$$
y-y_{1}=a(x-x_{1})
$$

## Integrasjon
### Ubestemte integraler
Et ubestemt integral er å finne alle antideriverte $F(x)$ til en funksjon $f(x)$ slik at $F'(x)=f(x)$.

Vi har følgende integrasjonsregler

| Forklaring         |    Funksjon    |                          Integrert                          |
| ------------------ |:--------------:|:-----------------------------------------------------------:|
| Konstant           |      $k$       |                           $kx+C$                            |
| Koeffisient        | $k \cdot f(x)$ |             $k \cdot \int f(x) \, \mathrm{d}x$              |
| Flere ledd         | $f(x)\pm g(x)$ | $\int f(x) \, \mathrm{d}x \pm \int g(x_{9}) \, \mathrm{d}x$ |
| Potensfunksjon     |     $x^r$      |          $\frac{1}{r+1}x^{r+1}+C,\,\,\, r \neq 1$           |
| Spesialtilfelle    | $\frac{1}{x}$  |             $\ln \vert x \vert +C,\,\, x\neq 0$             |
| Eksponentialfunk   |    $e^{kx}$    |                   $\frac{1}{k}e^{kx} +C$                    |
| Eksponentialfunk2  |    $a^{x}$     |    $\frac{a^{x}}{\ln a}+C \,\, ,\,\,a>0\wedge a \neq 1$     |

### Bestemt integral som grense av sum
Vi har en funksjon $f(x)$. Vi ønsker å finne arealet under grafen fra $x = a$ til $x = b$.

Vi forsøker å dele opp området under grafen i $n$ rektangler. Bredden på hvert rektangel må da være $\Delta x = \frac{b - a}{n}$. 

Hvis vi kaller $x$-verdien i starten av rektangelet for $x_{i}$ der $i = \{ 1,\ 2,\ 3,\ \ldots,\ n\}$ så vil høyden av hvert rektangelet være $f\left( x_{i} \right)$.

Siden arealet til et rektangel er høyde multiplisert med bredde vil summen av arealene til rektanglene altså være

$$S_{n} = f\left( x_{1} \right) \cdot \Delta x + f\left( x_{2} \right) \cdot \Delta x + f\left( x_{3} \right) \cdot \Delta x + \ldots = \sum_{i = 1}^{n}{f\left( x_{i} \right) \cdot \Delta x}$$

Hvis vi lar bredden av rektanglene bli veldig små slik at rektanglene egentlig bare blir infitesimalt smale striper får vi

$$\lim_{\Delta x \rightarrow 0}{S_{n} =}\lim_{\begin{array}{r}
n \rightarrow \infty \\
\Delta x \rightarrow 0
\end{array}}{\sum_{i = 1}^{n}{f\left( x_{i} \right) \cdot \Delta x}} = \int_{a}^{b}{f(x)\ \text{d}x}$$

### Fundamentalsetningen
Fundamentalsetningen eller analysens fundamentalteorem forteller oss at integrasjon og derivasjon er motsatte operasjoner.

La $f$ være en kontinuerlig funksjon på $[a, b]$. La

$$
F'(x)=f(x) \quad \text{for alle} \quad x\in[a, b]
$$
> Denne førsten delen av fundamentalsetningen forteller oss at alle kontinuerlige funksjoner $f$ har antideriverte funksjoner $F$. 

Da er 
$$
\int_{a}^{b} f(x) \, dx = \left[ F(x) \right] _{a}^b=F(b)-F(a)
$$

> Denne andre delen av fundamentalsetningen forteller oss at vi kan beregne et bestemt integral ved hjelp av det ubestemte integralet

### Areal under og mellom grafer
>[!todo]
>Ståle: fiks opp disse avsnittene

### Integrasjonsteknikker
#### Delvis integrasjon
>[!todo]
>Ståle: fiks opp disse avsnittene


Delvis integrasjon brukes ofte dersom du har et produkt av to ulike funksjoner, hvor den ene faktoren er enkel å integrere og den andre faktoren er enkel å derivere.

$$
\int u' \cdot v \, \mathrm{d}x = u \cdot v - \int u \cdot v' \, \mathrm{d}x 
$$

#### Variabelskifte
Variabelskifte brukes hvis du skal integrere en sammensatt funksjon. Variabelskifte kalles ofte for den omvendte kjerneregelen.

Velg en kjerne $u$ og deriver denne slik at du finner $u'=\frac{du}{dx}$

## Økonomi
Her lar vi $I(x)$ være inntektene ved salg av $x$ enheter og $K(x)$ være produksjonskostnadene ved produksjon av $x$ enheter. Overskuddet $O(x)$ er da gitt ved
$$
O(x)=I(x)-K(x)
$$

### Grenseinntekt og grensekostnad
Grenseinntekten $I'(x)$ er den deriverte av inntektsfunksjonen. Grenseinntekten $I'(x)$ forteller oss omtrent hvor mye vi tjener på å selge én mer enhet.

Grensekostnaden $K'(x)$ er den deriverte av kostnadsfunksjonen. Grensekostnaden $K'(x)$ forteller oss omtrent hvor mye det koster å produsere én mer enhet.

Vi bruker også begrepene *marginalinntekt* og *marginalkostnad*.

### Maksimalt overskudd
Vi har maksimalt overskudd når grenseinntekt er lik grensekostnad fordi
$$
\begin{aligned}
O'(x) &=0 \\
I'(x)-K'(x) &= 0\\
I'(x) &= K'(x)
\end{aligned}
$$
Hvis du får flere løsninger så bør du sjekke hvilke løsninger som er toppunkter.

### Enhetskostnader
Enhetskostnaden $E(x)$ fordeler produksjonskostnadene $K(x)$ på antall enheter $x$.
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
Vi setter uttrykket til den deriverte $E'(x)=0$ siden vi leter etter bunnpunktet til $E(x)$.
$$
\begin{aligned}
E'(x)=\frac{K'(x)\cdot x-K(x)\cdot1}{x^{2}}&=0\\
K'(x)\cdot x-K(x)\cdot1&=0\\
K'(x)\cdot x-K(x)&=0\\
K'(x)\cdot x &= K(x)\\
K'(x)&= \frac{K(x)}{x}\\
K'(x)&= E(x)\\
\end{aligned}
$$

### Etterspørsel

> **Kommentar fra Ståle**: Dette er pensum fra S1 i vårt læreverk. Andre læreverk lærer dette i S2. Jeg tror ikke det er relevant for eksamen, men jeg legger det ved her for sikkerhets skyld.

Etterspørselen $q$ er en funksjon av prisen $p$ slik at $q(p)$. Etterspørselen er også lik antall solgte enheter $x$ slik at
$$
x=q(p)
$$
Inntektene er $\text{pris} \times \text{antall solgte}$ eller $I(x)=p \cdot x$. Hvis vi bytter ut $x$ med $q(p)$ så får vi $I(p)=p\cdot q(p)$

På samme måte kan vi vise at kostnadene blir $K(x)=K(q(p))$.

## Matematisk notasjon

### Funksjoner

| Notasjon           | Forklaring                                                  |
| ------------------ | ----------------------------------------------------------- |
| $f(x)$             | $f$ er en funksjon av den uavhengige variabelen $x$         |
| $D_{f}=\mathbb{R}$ | Definisjonsmengden til $f$ er alle reelle tall $\mathbb{R}$ |
| $V_{f}=\mathbb{R}$ | Verdimengden til $f$ er alle reelle tall $\mathbb{R}$       |

### Mengder

| Notasjon                                                                  | Forklaring                                                                                                                     |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| $0\leq x$                                                                 | 0 er mindre eller lik $x$, eller sagt på en annen måte: $x$ er større eller lik null                                           |
| $[a, b]$                                                                   | Det lukkede intervallet fra $a$ til $b$ inneholder alle tall fra og med $a$ og opp til og med $b$                              |
| $\langle a,b \rangle  = \left( a, b \right)$                                                     | Det åpne intervallet fra $a$ til $b$ inneholder alle tall fra (men ikke inkludert) $a$ og opp til (men ikke inkludert) $b$. Hakeparenteser er vanlig på norsk, vanlige parenteser i vanlig i engelsk litteratur.     |
| $\langle \leftarrow,0]$                                                   | Er intervallet fra minus uendelig til og med 0                                                                                 |
| $x \in \mathbb{R}$                                                        | $x$ er element i mengden alle reelle tall $\mathbb{R}$                                                                         |
| $x \in \mathbb{N}$                                                        | $x$ er element i mengden alle naturlige tall $\mathbb{N}$                                                                      |
| $x \in [0, 20]$                                                            | $x$ er et reelt tall i det lukkede intervallet fra 0 til 20                                                                    |
| $x \in \langle \leftarrow,-1 \rangle \cup \langle 2, \rightarrow \rangle$ | $x$ er element i unionen ($\cup$) av to ulike intervaller. Du kan ofte få svar som dette når du skal løse andregradsulikheter. |
| $D_{f}=\mathbb{R} \setminus 1$                                            | Definisjonsmengden til $f$ er mengden av alle reelle tall bortsett fra 1.                                                                                                                               |

### Logikk

| Notasjon | Eksempel               | Forklaring                                                         |
| ----------- | ----------------------- | --------------------------------------------------------------- |
| $a \iff b$ | $2x=4\iff x=2$         | Ekvivalens. $a$ er riktig hvis og bare hvis $b$ er riktig          |
| $a \implies b$ | $x=2 \implies x^{2}=4$ | Implikasjon. $b$ er riktig hvis $a$ er riktig                      |
| $a \wedge b$ | $x=0 \wedge x=4$       | $\wedge$ betyr og samtidig. Her må $x$ være lik 0 og 4 samtidig.   |
| $a \vee b$  | $x=0 \vee x=2$         | $\vee$ betyr eller. Altså $x=0$ eller $x=2$ eller $x=0 \wedge x=2$ |

### Spesielle tegn
#### Sum
Summen av en tallfølge der elementene heter $a_{1}, a_{2}, a_{3}$ og så videre er gitt ved
$$
s_{n}=\sum_{i=1}^n a_{i}
$$

#### Derivasjon
La $f(x)$ være en kontinuerlig funksjon. Den deriverte kan da skrives som
$$
f'(x)=\frac{df}{dx}(x)=\frac{d}{dx}f(x)=\dot{f}
$$

#### Integrasjon
Integralet av $f(x)$ fra $a$ til $b$ kan skrives som 
$$
\int_{a}^{b} f(x) \, \mathrm{d}x = \left[ F(x) \right] _{a}^{b}=F(b)-F(a)
$$

[^1]: Merk at `python`-lister begynner på indeks 0. Det vil si at for å hente ut det første elementet i ei liste som heter `min_liste` så skriver vi `min_liste[0]`. For å hente du det fjerde elementet i lista skriver vi `min_liste[3]`.
