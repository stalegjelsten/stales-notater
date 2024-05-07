---
{"dg-publish":true,"permalink":"/Kunnskap/Typiske algebrafeil/","title":"Typiske algebrafeil","tags":["s2"]}
---


## Typiske algebrafeil
> Algebra er vanskelig, men så lenge du ikke gjør noe ulovlig så går det som oftest greit.

I T-, R- og S-matte på videregående så er du nødt til å være god i algebra for å få vist kompetansen din på del 1. I dette notatet har jeg samlet noen vanlige feil som jeg ser at mange elever gjør.

### Forkorting av brøker med bokstavuttrykk
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

#### Løsning: forkorting av brøker med bokstavuttrykk
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


#### Å løse opp parentes med eksponent
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

#### Løsning: løse opp parentes med eksponent
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

<!--

## Video som oppsummerer vanlige feil

<iframe src="https://www.youtube.com/embed/9YwPjwdLrbw?si=pMQ7_P-G4-QcWg76&t=2m49s" class="youtube" title="https://youtu.be/9YwPjwdLrbw?si=pMQ7_P-G4-QcWg76&t=2m49s" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
-->
