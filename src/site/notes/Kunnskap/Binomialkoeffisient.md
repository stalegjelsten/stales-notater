---
{"dg-publish":true,"permalink":"/Kunnskap/Binomialkoeffisient/","title":"Binomialkoeffisient","tags":["matematikk"]}
---


# Binomialkoeffisient
Binomialkoeffisienter skrives som $\binom{n}{k}$ og leses som «$n$ over $k$».

For å bestemme verdien av binomialkoeffisienten gjør vi:
$$
\binom{n}{k} = \frac{n!}{k! \cdot (n-k)!}
$$
der $n!$ er [[Kunnskap/Fakultet\|fakultetsfunksjonen]] til $n$. 

## Raskere regnemetode for binomialkoeffisienter
Vi kan forenkle beregningene ved å kun regne ut
$$
\binom{n}{k}= \frac{\prod_{i=k+1}^{n}i}{(n-k)!}
$$
For eksempel blir
$$
\binom{8}{4}= \frac{\prod_{i=(4+1)}^{8}i}{(8-4)!}= \frac{5 \cdot 6 \cdot 7 \cdot \cancel{ 8 }}{1 \cdot \cancel{ 2 } \cdot 3 \cdot \cancel{ 4 }} = \frac{5 \cdot 6 \cdot 7}{3} = 5 \cdot 2 \cdot 7= 70
$$
Å bruke formelen her er litt vanskelig, så dette er min algoritme for å finne binomialkoeffisientene.

1. Finn $m=\min(k, (n-k))$.   
    - Velg altså det minste av $k$ og $(n-k)$
	 - $m$ bestemmer antall faktorer i teller og nevner
2. Sett opp en brøkstrek
3. I telleren starter du med $n$ og multipliserer med heltallene nedover. $m$ er antall faktorer.
4. I nevneren starter du med 1 og multipliserer med heltallene oppover. $m$ er antall faktorer.

### Eksempel
Vi skal bestemme $\binom{12}{9}$. Da er $m=\min(9, (12-9))=3$.
$$
\binom{12}{9}= \frac{12 \cdot 11 \cdot 10}{1 \cdot 2 \cdot 3}= \frac{1320}{6} = 220
$$


## Kobling til Pascals trekant

![](https://upload.wikimedia.org/wikipedia/commons/0/03/Pascal%27s_Triangle_rows_0-16.svg)

Vi kan bestemme binomialkoeffisienter ved hjelp av Pascals trekant. 

Binomialkoeffisienten til $\binom{n}{k}$ vil være tall nummer $(k+1)$ i rad $(n+1)$. 

For eksempel vil $\binom{8}{4}$ være det $(4+1)=5$. tallet som ligger i rad $(8+1)=9$ (fra toppen). Altså: $\binom{8}{4}=70$

