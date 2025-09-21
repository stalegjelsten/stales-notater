---
{"dg-publish":true,"permalink":"/Kunnskap/Totallsystemet/","title":"Totallsystemet"}
---


Totallsystemet eller det binære tallsystemet bruker sifrene 0 og 1 for å representere tall. Et eksempel på et slikt tall er $1010_{2}$. Legg merke til at vi bruker tegnet $_2$ for å markere at tallet er skrevet i totallsystemet.

>[!tip] Hva brukes totallsystemet til?
>
> Alle datamaskiner og digitale kretser benytter seg av totallsystemet. Hvert siffer i et tall som $0100 \thinspace 0001_{2}$ kalles en bit, og 8 bit utgjør en byte. Tallet $0100 \thinspace 0001_{2}$ består altså av 8 bits eller 1 byte.
>
> Byten $0100 \thinspace 0001_{2}$ er kode for bokstaven A i datamaskiner[^1], slik at hver gang du ser en A på skjermen så «tenker» datamaskinen $0100 \thinspace 0001_{2}$ .

I totallsystemet bruker vi tallet 2 som grunntall. La oss sette tallet $1010_{2}$ inn i nederste rad i en tabell med toerpotensene[^2]. 

| Toerpotens          |         $2^3$          |         $2^2$          |           $2^1$           |          $2^0$           |
| ----------- | :----: | :----: | :----: | :----: |
| Toerpotens utregnet |          $8$           |          $4$           |            $2$            |           $1$            |
| Tallet $1010_{2}$   | $\textcolor{brown}{1}$ | $\textcolor{dgreen}{0}$ | $\textcolor{dblue}{1}$ | $\textcolor{dred}{0}$ |

Vi kan bruke tabellen til å se at tallet vårt egentlig består av $\textcolor{brown}{1}$ åtter, $\textcolor{dgreen}{0}$ firere, $\textcolor{dblue}{1}$ toer og $\textcolor{dred}{0}$ enere.

En åtter og en toer blir 10. Vi kan sette opp regnestykket på følgende måte *dersom* vi ønsker å vise fullstendig utregning.
$$
\begin{aligned}
\textcolor{brown}{1} \cdot 2^{3} + \textcolor{dgreen}{0} \cdot 2^{2} + \textcolor{dblue}{1} \cdot 2^{1} + \textcolor{dred}{0} \cdot 2^{0} \\ 
\textcolor{brown}{1} \cdot 8 + \textcolor{dgreen}{0} \cdot 4 + \textcolor{dblue}{1} \cdot 2 + \textcolor{dred}{0} \cdot 1 \\ 
\textcolor{brown}{8}+ 0 + \textcolor{dblue}{2} + 0 \\ 
\textcolor{brown}{8}+ \textcolor{dblue}{2}\\ 
\underline{\underline{10}}
\end{aligned}
$$

## Omgjøring fra totallsystemet til titallsystemet
Vi kan alltid bruke en tabell for å gjøre om fra totallsystemet til titallsystemet. La oss se på et vanskeligere eksempel med $1001 \thinspace 0111_{2}$. Vi ser at tallet har 8 ulike sifre, derfor må vi lage en tabell med 8 kolonner. Denne gangen velger jeg å bare skrive toerpotensene på utregnet form i rad 1 og jeg setter inn tallet i rad 2.


| Toerpotens utregnet               | $128$ | $64$ | $32$ | $16$ | $8$ | $4$ | $2$ | $1$ |
| --------------------------------- | :---: | :--: | :--: | :--: | :-: | :-: | :-: | :-: |
| Tallet $1001 \thinspace 0111_{2}$ |   1   |  0   |  0   |  1   |  0  |  1  |  1  |  1  |

Vi har altså  1 stk 128, 1 stk 16, 1 firer, 1 toer og 1 ener. Vi kan enkelt legge sammen disse verdiene for å finne ut hva tallet blir i titallsystemet:
$$
128+16+4+2+1=\underline{\underline{151}}
$$

## Omgjøring fra titallsystemet til totallsystemet
For å gjøre om fra titallsystemet til totallsystemet så kan vi dele på 2 mange ganger og sjekke om vi får rest eller ikke.

I eksempelet nedenfor så gjør vi om tallet 29 til totallsystemet. Vi starter med 29 og deler på 2. Svaret blir 14 med 1 i rest. Jeg noterer meg resten og tar deretter svaret mitt (14) og deler på 2 igjen.

![Omgjøring fra titallsystemet til totallsystemet](/img/user/_resources/omgjøring-titallsystemet-til-totallsystemet.png)

Etter litt trening så trenger man ikke skrive ut utregningene, man klarer seg med tabellen som dere ser til høyre. For å sette sammen tallet i totallsystemet så leser vi fra bunn og oppover i tabellen. 29 i titallsystemet tilsvarer $11101_{2}$ i totallsystemet.

>[!tip] Hvor mange typer mennesker finnes det?
>
> Det finnes 10 typer mennesker i verden. De som forstår binære tall og de som ikke gjør det.

[^1]: Ved bruk av «vanlig» [ASCII-koding](https://no.wikipedia.org/wiki/ASCII) av bokstaver
[^2]: Toerpotensene er $2^{0},2^{1},2^{2},2^{3}$ og så videre. Når vi regner dem ut så får vi $1,2,4,8,16,32,64,\dots$