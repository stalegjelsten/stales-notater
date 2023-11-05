---
{"dg-publish":true,"permalink":"/Kunnskap/Formelark S2/","title":"Formelark S2","tags":["s2"]}
---


## Følger, rekker og lån
En tallfølge er en ordnet liste med tall: $a_{1}, a_{2}, a_{3}, a_{4}, \dots, a_{n}$

En rekke er summen av tallene i en tallfølge. Delsummen $s_{n}$ av de $n$ første leddene i en følge er gitt ved
$$
\sum_{i=1}^n a_{i}=a_{1}+ a_{2}+a_{3}+a_{4}+\dots+a_{n}
$$

| Forklaring                           | Formel                                   |
| :------------------------------------ | :---------------------------------------- |
| Ledd i aritmetisk følge (rekursiv)   | $a_{n + 1} = a_{n} + d$               |
| Ledd i aritmetisk følge (eksplisitt) | $a_{n} = a_{1} + (n-1)\cdot d$        |
| Ledd i geometrisk følge (rekursiv)   | $a_{n + 1} = a_{n} \cdot k$           |
| Ledd i geometrisk følge (eksplisitt) | $a_{n} = a_{1} \cdot k^{n-1}$          |
| Aritmetisk rekke (sum av følge)      | $s_{n}=\frac{a_{1}+a_{n}}{2}\cdot n$   |
| Geometrisk rekke (sum av følge)      | $s_{n}=a_{1}\cdot \frac{k^{n}-1}{k-1}$ |
| Uendelig geometrisk rekke            | $-1<k<1 \implies s=\frac{a_{1}}{k-1}$   |

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
>Lag et program som skriver ut de første n leddene i denne følgen. Hvis programmet ditt fungerer riktig vil du få $a_50  = 11986911799691$.

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
Funksjonsdrøfting er handler om å finne ut hvordan funksjoner ser ut når du tegner dem. Vi er som oftest interessert i

- Nullpunkter finner du ved å sette $f(x)=0$
- Topp-, bunn- og terrassepunkter finner du ved å sette $f'(x)=0$
- Monotoniegenskaper: når funksjonen stiger og synker finner du ved å sjekke når $f'(x)>0$ og $f'(x)<0$. Du trenger å faktorisere og tegne fortegnslinje for å finne ut av dette.
- Vendepunkter finner du ved å sette $f''(x)=0$
- Krumning finner du ved å sjekke når $f''(x)>0$ og $f''(x)<0$. Du trenger å faktorisere og tegne fortegnslinje for å finne ut av dette.

### Logaritmer
#### Egenskaper ved logaritmefunksjoner
En logaritmefunksjon er den inverse funksjonen til en eksponentialfunksjon.

- Eksponentialfunksjonen $f(x)=10^{x}$ har tilhørende logaritmefunksjon $\log_{10}x$ eller ofte bare kalt $\log x=\lg x$.
- Eksponentialfunksjonen $f(x)=e^{x}$ har tilhørende logaritmefunksjon $\ln x$
- Eksponentialfunksjonen $f(x)=a^{x}$ har tilhørende logaritmefunksjon $\log_{a}x$ for $a>0$ (det finnes altså uendelig mange typer eksponentialfunksjoner og logaritmefunksjoner)

Siden logaritmefunksjonen og eksponentialfunksjonene er inverse så har vi følgende sammenhenger:
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

Merk at den siste regelen forteller oss hvor logaritmefunksjonene har sitt eneste nullpunkt. For $f(x)=\ln x$ vil funksjonen være negativ for $0<x<1$ og positiv for alle $x>1$.

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

- Vi får vertikale asymptoter i bruddpunktene
	- Mulig å finne ved å løse $Q(x)=0$
- Vi får horisontale asymptoter dersom $P$ og $Q$ har samme grad
	- Mulig å finne ved å dividere leddene med høyest grad på hverandre
- Vi får skrå asymptoter når graden av $P$ er én større enn graden av $Q$
	- Mulig å finne ved å ta polynomdivisjon. Den skrå asymptoten er svaret på divisjonen når du ser bort fra resten.

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

[^1]: Merk at `python`-lister begynner på indeks 0. Det vil si at for å hente ut det første elementet i ei liste som heter `min_liste` så skriver vi `min_liste[0]`. For å hente du det fjerde elementet i lista skriver vi `min_liste[3]`.
