---
{"dg-publish":true,"permalink":"/Publisert/Løsningsforslag S2 eksamen V2023/","title":"Løsningsforslag S2 eksamen V2023","tags":["matematikk","løsningsforslag","S2"]}
---


# Løsningsforslag S2 eksamen V2023
Skrevet av Ståle Gjelsten 24. mai 2023. Jeg setter veldig pris på om du melder ifra om feil eller unøyaktigheter på forumet på [matematikk.net](https://matematikk.net)

## Del 1

### Oppgave 1
$$\int_0^1 \left( e^{ x }+2x^2 \right)  \,\mathrm{d}x = \left[e^x+ \cancel{ \frac{3}{3} }  x^3 \right]_0^1 = e^1+1^3- \left( \underbrace{ e^0 }_{ =1 }+0^3 \right) = e+1- 1 = \underline{\underline{e}}$$

### Oppgave 2

#### 2a
Når det blir produsert 40 enheter kan vi finne en tilnærmet verdi for grensekostnaden $K'(40)$ ved å lage en tangent til $K(x)$ i $(40, K(40))$.

Jeg forsøkte å legge en tangent i punktet, og fikk stigningstallet $a=\frac{9000}{120}=75$. 

$$\underline{\underline{K'(40)\approx 75 \, \mathrm{kr/enhet}}}$$

#### 2b
Jeg vet at overskuddet blir størst når $O'(x)=I'(x)-K'(x)=0 \iff I'(x)=K'(x)$, altså når stigningstallene til inntektsfunksjonen og kostnadsfunksjonen er like store. 

Det ser ut til stigningstallene er like store omtrent ved $x=55$. Det stemmer også godt med at differansen mellom inntekt og kostnad ser ut til å være stor ved $x=55$.

**Vi har størst overskudd ved produksjon av omtrent 55 enheter.**

### Oppgave 3

#### 3a
Siden summen av sannsynlighetene skal være lik 1 må

$$
\begin{aligned}
\sum P(X=x) &= 1\\
k+0,3+k-0,2+0,1&=1\\
2k &= 1 -0,3-0,1+0,2\\
2k &=0,8\\
k &= 0,4
\end{aligned}
$$

Dermed er:

$$P(X>1)=P(X=2)+P(X=3)=(0.4-0.2) + 0.1 = \underline{\underline{0,3}}$$

#### 3b
|            $x$             |  0  |  1  |  2  |  3  | Sum |
|:------------------------:|:---:|:---:|:---:|:---:| :---:|
|         $P(X=x)$         | 0,4 | 0,3 | 0,2 | 0,1 |   1 |
|     $x\cdot P(X=x)$      |  0  | 0,3 | 0,4 | 0,3 |   1 |
| $(x-\mu)^2 \cdot P(X=x)$ | 0,4 |  0  | 0,2 | 0,4 |  1   |

Forventningsverdien er $\text{E}(X) = \sum x\cdot P(X=x)=\underline{\underline{1}}$.  
Variansen er $\text{Var}(X)=\sum (x-\mu)^2\cdot P(X=x)=\underline{\underline{1}}$.  

### Oppgave 4

#### 4a
Det ser ut til at eleven forsøker å regne ut delsummer av en aritmetisk rekke. Helt konkret ser det ut til at eleven forsøker å regne ut summen av de ti første leddene når startverdien er 3 og differansen er 4, altså $S_{10},\, a_1=3,\, d=4$.

#### 4b
Vi kan finne summen av denne aritmetiske rekka med:

$$s_{100}= \frac{a_{1}+a_{100}}{2}\cdot 100 = \frac{3+(3+4\cdot 99)}{2}\cdot{100}=\frac{402}{2}\cdot {100}=\underline{\underline{20\,100}}$$

### Oppgave 5
Den første dagen får Knut tilført 7 mg virkestoff, andre dag så er mengden virkestoff redusert til $7 \,\text{mg}\cdot 0.9 = 0.63 \,\text{mg}$, samtidig som han får tilført nye $7$ mg. 

På dag $n$ så vil derfor Knut ha den samlede mengden:

$$\sum_{i=0}^n 7\cdot 0,9^i$$

Dette er en geometrisk rekke som konvergerer når $n\to \infty$, siden $-1<k<1$. Derfor kan vi finne summen av rekka med:

$$s_n = \frac{a_1}{1-k}=\frac{7}{1-0,9}=70$$

Mengden virkestoff hos Knut vil aldri overstige 70 mg. **Legens påstand er riktig**.

### Oppgave 6

#### 6a
Siden vi skal finne $P(X>600)$ og 600 ligger nøyaktig to standardavvik over forventningsverdien kan vi bare slå opp på $z=2.0$ i normalfordelingstabellen for å bestemme $P(X<600) = \Phi(2) = 0.9772$.

$$P(X>600) = 1-P(X<600) = 1-0,9772 = \underline{ \underline{0.0228}}$$

#### 6b
Sannsynligheten for at levetiden er *kortere* enn $t$ timer er 24,2 prosent. Jeg bruker normalfordelingstabellen og finner $\Phi(z) = 0.242 \implies z=-0.70$.

$$
\begin{aligned}
z &= \frac{t-\mu}{\sigma}\\
z\sigma + \mu &\overset{ \rightleftarrows  }{ = } t\\
t &= -0.70\cdot 50 + 500\\
t &= -35 + 500\\
t &= 465
\end{aligned}
$$

**Det er 75,8 % sannsynlighet for at et tilfeldig valgt batteri har levetid mer enn 465 timer.**

#### 6c
Siden forventningsverdien er 500 må toppunktet til normalfordelingsfunksjonen ligge ved $x=500$. Det stemmer med graf A og D.

I tillegg vet vi at standardavviket er 50. Hvis vi beveger oss et standardavvik mot høyre eller venstre fra forventningsverdien skal vi komme til vendepunktene til normalfordelingsfunksjonen. Det ser ut til å stemme bra med graf A, hvor vendepunktene ligger ved omtrent $x=450$ og $x=550$.

**Graf A illustrerer $X$.**

## Del 2

### Oppgave 1

#### 1a
Annuitetslån har faste terminbeløp slik at lånebeløpet er lik produktet terminfaktoren multiplisert med terminbeløpet: $L=F\cdot T$.
Vi kan beregne terminfaktoren $F$ ved:

$$
\begin{aligned}
F &= \frac{1-\frac{1}{v^n}}{v - 1}\\
F &= \frac{1-\frac{1}{1,0049^{36}}}{1,0049 - 1}\\
F &= 32,93\\
\end{aligned}
$$

Og terminbeløpet blir da

$$
\begin{aligned}
L &= F\cdot T\\
T &= \frac{L}{F} = \frac{150\,000}{32,93}=\underline{\underline{4555,14}}
\end{aligned}
$$

**Terminbeløpet er 4555,14 kr.**

#### 1b
Jeg bruker en ferdig regnearkmodell jeg hadde liggende til å løse denne oppgaven. Fra regnearket ser jeg at restlånet *før* 25. innbetaling er 52 959,79 kr. **Dermed vil erstatningen fra forsikringsselskapet dekke restlånet** (gitt at han betaler restlånet med en gang han får erstatningen). Se utklippet under.

![](/img/user/_resources/s2-v23-del2-oppg1a1.png)

![](/img/user/_resources/s2-v23-del2-oppg1a2.png)

### Oppgave 2

#### 2a
Jeg brukte regresjonsverktøyet i GeoGebra valgte den logistiske modellen:

$$\underline{\underline{F(x)=\frac{660,37}{1+30,72\,e^{-0,7066x}}}}$$

Logistiske funksjoner flater ut ved en horisontal asymptote (i dette tilfellet 660,37 millioner kr). Selv om det kanskje høres usannsynlig ut at markedet for musikkstrømming ikke kommer til å vokse, så tror jeg at nærmest all musikklytting *allerede* er blitt flyttet fra formater som CD og nedlasting, til strømming. Derfor er det usannsynlig veksten kommer til å fortsette i samme tempo. En logistisk modell har også asymptote ved $y=0$. Det stemmer også godt med at strømmemarkedet var svært lite (kanskje ikke-eksisterende?) i Norge før Spotify ble lansert i 2008.

*Kommentar: Man kan også argumentere for andre regresjonsmodeller, f.eks. vil en tredjegradsmodell passe fint. Vær imidlertid klar over at tredjegradsmodellen sannsynligvis vil ha et mindre gyldighetsområde siden denne har negativ vekstfart både før 2008 og etter 2018. Sensorveiledninga sier at flere ulike modeller kan gi full uttelling så lenge de begrunnes godt.* 

![](/img/user/_resources/s2-v23-del2-oppg-2a.png)

#### 2b
Se utklippet fra CAS.

![](/img/user/_resources/s2-v23-del2-oppg-2b.png.png)

$$
\begin{aligned}
I&=3729,0\\
G&=344,5\\
S&=3729,1\\
D&=116,3
\end{aligned}
$$

#### 2c
$I$ beregner integralet under $F$ fra $x=-0.5$ til $x=10.5$. Dette gir en tilnærmingsverdi for de samlede inntektene fra musikkstrømming i Norge fra og med 2008 til og med 2018. De samlede inntektene er omtrent 3729 millioner kr.

$G$ finner en tilnærmingsverdi de samlede inntektene fra og med 2011 til og med 2015 ved å integrere, deretter divideres svaret med 5. $G$ finner altså de gjennomsnittlige årlige inntektene mellom år 2011 og 2015. De gjennomsnittlige årlige inntektene i perioden er 344,5 millioner kr.

$S$ gir oss de samlede inntektene fra 2008 til 2018 beregnet som summen av en rekke, altså ved å legge sammen inntektene i hvert år. De samlede inntektene i perioden er omtrent 3729 millioner kr.

$D$ gir oss omtrent momentan vekstfart i 2013. Vi kjenner igjen uttrykket for den deriverte hvor vi har $f'(x)=\lim_{ h \to 0 } \frac{f(x+h)-f(x)}{h}$. Her er $x=5$ og $h=0.001$. Den momentane vekstfarten i 2013 er omtrent 116,3 millioner kr per år.

### Oppgave 3

#### 3a
Vi starter med noen antagelser:

- Birger velger *helt* tilfeldig om han fyller hvert enkelt glass med Pepsi-Cola eller Coca-Cola
- Marte tipper *helt* tilfeldig for hvert colaglass
- Marte glemmer hva hun har gjettet på de forrige glassene, og smaken setter seg ikke i munnen hennes slik at vi kan anta at forsøkene er uavhengige

Vi kan da behandle dette som et binomisk forsøk med $n=10$ og $p=0.5$.

Vi kan beregne denne sannsynligheten enkelt i GeoGebra, eller med formelen:

$$
P(X=6)=\binom{n}{k}\cdot p^k \cdot(1-p)^{n-k} = \frac{10!}{6!(10-6)!} \cdot {0}.5^6  \cdot 0.5^4= \underline{\underline{0,205}}
$$

#### 3b
Vi lar $p$ være sannsynligheten for at Marte klarer å gjette riktig og $X$, antall riktige gjetninger, er testobservator. 

Det skal mye til at Marte er dårligere til å gjenkjenne colaene enn ved tilfeldig gjetting, og jeg er egentlig kun interessert i å finne ut om hun *bedre* enn tilfeldig gjetning. Derfor velger jeg en ensidig hypotesetest. Vi skal bruke signifikansnivået $\alpha=0,05$.

$$
\begin{aligned}
H_{0}&: \quad p=0.5 \\ 
H_{1}&: \quad p>0,5 \\
\end{aligned}
$$

![](/img/user/_resources/s2-v23-del2-oppg-3b.png.png)
Ved hjelp av GeoGebra finner jeg at $P(8\leq X)=0,0547$ gitt at $H_{0}$ er sann. 

Siden sannsynligheten $P(8\leq X)=0,0547$ er større enn signifikansnivået $\alpha = 0.05$ så **kan vi *ikke* forkaste $H_0$.**

#### 3c
	
![](/img/user/_resources/s2-v23-del2-oppg-3c.png)

Jeg brukte sannsynlighetsverktøyet i GeoGebra og endret antallet, $n$, til 30. Deretter dro jeg den lille svarte pila den bortover langs $x$-aksen fram til den beregnede sannsynligheten var mindre enn $0.05$. Det skjedde ved $P(20\leq X)$.

**Dersom Marte gjetter riktig på minst 20 glass så kan hun overbevise Birger om at hun er bedre til å gjenkjenne cola enn en tilfeldig gjetter med et signifikansnivå på 5 %.**

### Oppgave 4
Jeg gjorde disse oppgavene i Excel, se regnearket under.

![](/img/user/_resources/s2-v23-del2-oppg-4a.png.png)

#### 4a
De ukentlige beløpene for de fire første ukene er markert i blått i utklippet. Det venstre blå rektangelet viser beløpene for tilbud 1, det høyre blå rektangelet viser beløpene for tilbud 2. Vi kan se at tilbud 1 vokser fortere enn tilbud 2 i starten.

#### 4b
**I uke 28 så vil tilbud 2 for første gang gi større utbetaling enn tilbud 1**, se den røde markering i Excel-arket.

#### 4c
**I uke 39 så vil tilbud 2 for første gang ha gitt større *samlet utbetaling* enn tilbud 1**, se den gule markeringen i Excel-arket.

### Oppgave 5

#### 5a
Se programmet under. 
```python
from scipy.stats import norm # henter nødvendige pakker for normalfordeling
from random import randint

n = 20
sum_karakterer = 0
for i in range(n):
    # trekker et tilfeldig tall fra 1 til 3. Dette tilsvarer
    # skole A, B og C
    skole = randint(1,3)
    if skole == 1:
        # hvis det tilfeldige tallet er 1, så skal vi trekke 
        # tilfeldig elev fra skole A. I dette tilfellet har 
        # normalfordelingen my = 3.8 og sigma = 1.2             
        # # vi trekker en tilfeldig elev med norm.rvs()
        elev = norm.rvs(3.8,1.2)
    elif skole == 2:
        elev = norm.rvs(3.4,1.4)
    else:
        elev = norm.rvs(4.1,1.1)
    # vi legger til elevens karakter på summen
    sum_karakterer += elev

print(f"Gjennomsnittskarakteren til de {n} elevene er {sum_karakterer/n:.3f}.")
```

#### 5b
```python
from scipy.stats import norm # henter nødvendige pakker for normalfordeling
from random import randint

N = 10_000
antall_gunstige = 0
for j in range(N):
    n = 20
    sum_karakterer = 0
    for i in range(n):
        # trekker et tilfeldig tall fra 1 til 3. 
        # Dette tilsvarer skole A, B og C
        skole = randint(1,3)
        if skole == 1:
            # hvis det tilfeldige tallet er 1, så skal vi trekke 
            # tilfeldig elev fra skole A. I dette tilfellet har 
            # normalfordelingen my = 3.8 og sigma = 1.2             
            # # vi trekker en tilfeldig elev med norm.rvs()
            elev = norm.rvs(3.8,1.2)
        elif skole == 2:
            elev = norm.rvs(3.4,1.4)
        else:
            elev = norm.rvs(4.1,1.1)
        # vi legger til elevens karakter på summen
        sum_karakterer += elev
    if sum_karakterer/n > 4:
        # hvis snittkarakteren er over 4 så har vi et gunstig utfall
        antall_gunstige += 1

print(f"Etter {N} simuleringer estimerer jeg at sannsynligheten for at"
      f"gjennomsnittskarakteren er over 4 til {antall_gunstige/N:.4f}.")
```

Jeg brukte $10\,000$ simuleringer og testet programmet noen ganger. Jeg så at estimatene mine lå mellom 0,200 og 0,210. Siden avvikene er små og programmet allerede bruker 6-7 sekunder på å kjøre, så velger jeg å ikke øke antall simuleringer, $N$, for å oppnå bedre nøyaktighet.

**Sannsynligheten for at gjennomsnittskarakteren til de 20 elevene er over 4 er estimert til 0,205 ved hjelp av programmet over.**
