---
{"dg-publish":true,"permalink":"/Løsningsforslag S2 eksempelsett 2022/","title":"Løsningsforslag S2 eksempelsett 2022","tags":[null]}
---


# Løsningsforslag S2 eksempelsett 2022

## Del 1 oppgave 3
### Om oppgaveteksten
Denne oppgaven finnes i to ulike varianter (sannsynligvis på grunn av en skrivefeil i løsningsforslag eller oppgavesettet. Den ene varianten sier at summen av de tre første leddene er 38/9, mens den andre varianten sier at summen av de seks første leddene er 38/9. Løsningsmetoden min vil fungere uansett hvilken variant man tenker seg, men det er nok lurt å heller formel for sum av geometrisk rekke ($s_{n} = a_{1} \frac{k^n-1}{k-1}$) enn min framgangsmåte dersom man får oppgitt summen av et høyt antall ledd. Min metode er enkel når du bare trenger å tenke på 3 ledd, men skal du ta hensyn til 100 så må du regne mye!

### Oppgavetekst
Summen av en uendelig geometrisk rekke konvergerer mot 6.

Sum av tre første ledd er 38/9

Hva er sum av de fire første?

### Løsningsforslag
Jeg kaller første ledd i rekka for $x$. Vet da at de tre første leddene må være:

$$x+xk+xk^2=\frac{38}{9}$$

Som kan faktoriseres til 

$$x(1+k+k^2)=\frac{38}{9}$$

Summen for uendelig geometrisk rekke gir:

$$\frac{x}{1-k}=6$$

Løser den likningen for $x$ og setter inn i uttrykket for sum av 3 første ledd 

$$x=6(1-k)$$

$$6(1-k)(1+k+k^2)=\frac{38}{9}$$
$$(1-k)(1+k+k^2)=\frac{38}{9\cdot 6}=\frac{38}{54}=\frac{19}{27}$$

$$1+k+k^2-k-k^2-k^3=\frac{19}{27}$$

$$1-k^3=\frac{19}{27}$$

$$k^3=1-\frac{19}{27}=\frac{8}{27}\Rightarrow \underline{k=\frac{2}{3}}$$

Vi har nå funnet $k$ og kan enkelt finne $x$:

$$x=6 (1-k)=6\left( 1- \frac{2}{3} \right)=6 \frac{1}{3}=2$$

Ledd 4 må være:

$$xk^3=2 \cdot \frac{8}{27}=\frac{16}{27}$$

Summen av de fire første leddene blir da summen av de tre første pluss dette fjerde leddet

$$\frac{38}{9}+\frac{16}{27}=\frac{114}{27}+\frac{16}{27}=\frac{130}{27}$$

Summen av fire første ledd er 

$$\underline{\underline{\frac{130}{27}}}$$
