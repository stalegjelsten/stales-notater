---
{"dg-publish":true,"permalink":"/Kunnskap/Formelark S2/","title":"Formelark S2","tags":["s2"]}
---


## Følger og rekker

| Forklaring                           | Formel                                   |
| ------------------------------------ | ---------------------------------------- |
| Ledd i aritmetisk følge (rekursiv)   | $$a_{n + 1} = a_{n} + d $$               |
| Ledd i aritmetisk følge (eksplisitt) | $$a_{n} = a_{1} + (n-1)\cdot d $$        |
| Ledd i geometrisk følge (rekursiv)   | $$a_{n + 1} = a_{n} \cdot k $$           |
| Ledd i geometrisk følge (eksplisitt) | $$a_{n} = a_{1} \cdot k^{n-1}$$          |
| Aritmetisk rekke (sum av følge)      | $$s_{n}=\frac{a_{1}+a_{n}}{2}\cdot n$$   |
| Geometrisk rekke (sum av følge)      | $$s_{n}=a_{1}\cdot \frac{k^{n}-1}{k-1}$$ |
| Uendelig geometrisk rekke            | $$-1<k<1 \implies s=\frac{a_{1}}{k-1} $$   |

### Rekker og konvergens
Ei rekke konvergerer og har summen $s$ dersom summen $s_{n}$ av $n$ første leddene nærmer seg tallet $s$ når $n \to \infty$. Altså
$$\lim_{n \to \infty}{s_{n} = s}$$
Geometriske rekker er alltid konvergente når $k \in \left\langle - 1\ ,\ 1 \right\rangle$ eller skrevet på en annen måte: $-1<k<1$. Summen av disse rekkene er gitt ved formelen
$$
s=\frac{a_{1}}{k-1}
$$

### Nåverdi og lån
#### Nåverdi
Nåverdien $N$ til et fremtidig beløp $B$ er gitt ved 
$$
N=\frac{B}{v^{n}}
$$
Der $v$ er vekstfaktoren til kalkulasjonsrenta og $n$ er antall perioder.

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
| Bruke logaritme på likning | $$a=b \iff \ln a=\ln b$$         |
| Hente ned eksponent        | $$\ln a^{x}=x\ln a$$             |
| Logaritme til produkt      | $$ \ln (a\cdot b)=\ln a +\ln b$$ |
| Logaritme til kvotient     | $$ \ln \frac{a}{b}=\ln a-\ln b$$ |
| Nullpunkt til logaritmer   | $$\ln 1=0$$                                 |

Merk at den siste regelen forteller oss hvor logaritmefunksjonene har sitt eneste nullpunkt. For $f(x)=\ln x$ vil funksjonen være negativ for $0<x<1$ og positiv for alle $x>1$.

## Derivasjon
Definisjon: Hvis $f(x)$ er kontinuerlig i et punkt $x$ så er den deriverte i punktet:

$$f'(x) = \lim_{\Delta x \to 0}\frac{f(x + \Delta x) - f(x)}{\Delta x}$$

Den deriverte i et punkt er lik den momentane vekstfarten i punktet og dermed også lik stigningstallet til tangenten til $f$ i punktet.

| Forklaring        | Formel                          | Eksempel                                                 |
| ----------------- | ------------------------------- | -------------------------------------------------------- |
| Konstant funksjon | $$f(x) = k$$                    | $$f'(x) = 0$$                                         |
| Potensfunksjon    | $$f(x) = x^{r}$$                | $$f'(x) = r \cdot x^{r - 1}$$                         |
| Konstante koeff.  | $$f(x) = k \cdot g(x)$$         | $$f'(x) = k \cdot g'(x)$$                          |
| Summer            | $$f(x) = g(x) \pm h(x)$$        | $$f'(x) = g^{'(x)} \pm h'(x)$$                     |
| Produkt           | $$f(x) = u(x) \cdot v(x)$$      | $$f'(x) = u'(x) \cdot v(x) + u(x) \cdot v'(x)$$ |
| Kvotienter        | $$f(x) = \frac{u(x)}{v(x)}$$    | $$f'(x) = \frac{u'v - uv'}{v^{2}}$$             |
| Eksponentialfunk  | $$f(x) = e^{x}$$                | $$f'(x) = e^{x}$$                                     |
| Eksponentialfunk  | $$f(x) = a^{x}$$                | $$f'(x) = a^{x}\ln x$$                                |
| Logaritme         | $$f(x) = \ln x$$                | $$f'(x) = \frac{1}{x}$$                               |
| Kjerneregelen     | $$f(x) = g\left( u(x) \right)$$ | $$f'(x) = g'(u) \cdot u'(x)$$                   |

## Økonomi
Her lar vi $I(x)$ være inntektene ved salg av $x$ enheter og $K(x)$ være produksjonskostnadene ved produksjon av $x$ enheter. Overskuddet $O(x)$ er da gitt ved
$$
O(x)=I(x)-K(x)
$$

### Grenseinntekt og grensekostnad
Grenseinntekten $I'(x)$ er den deriverte av inntektsfunksjonen. Grenseinntekten $I'(x)$ forteller oss omtrent hvor mye vi tjener på å selge én mer enhet.

Grensekostnaden $K'(x)$ er den deriverte av kostnadsfunksjonen. Grensekostnaden $K′(x)$ forteller oss omtrent hvor mye det koster å produsere én mer enhet.

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

#### Laveste enhetskostnader
Vi har de laveste enhetskostnadene når $E'(x)=0$ og når $K'(x)=E(x)$ fordi
$$
\begin{aligned}
E(x)&=\frac{K(x)}{x}\\
E'(x)&=\frac{K'(x)\cdot x-K(x)\cdot1}{x^{2}}\\
\frac{K'(x)\cdot x-K(x)\cdot1}{x^{2}}&=0\\
K'(x)\cdot x-K(x)\cdot1&=0\\
K'(x)\cdot x-K(x)&=0\\
K'(x)\cdot x &= K(x)\\
K'(x)&= \frac{K(x)}{x}\\
K'(x)&= E(x)\\
\end{aligned}
$$

### Etterspørsel (fra S1)
Etterspørselen $q$ er en funksjon av prisen $p$ slik at $q(p)$. 

Etterspørselen er også lik antall solgte enheter $x$ slik at
$$
x=q(p)
$$

Inntektene blir $\text{pris} \times \text{antall solgte}$ slik at 

- $I(p)=p\cdot q(p)$
- $I(x)=p\cdot x$

Kostnadene blir $K(x)=K(q(p))$.