---
{"dg-publish":true,"permalink":"/Kunnskap/Formler i OneNote og Word/","title":"Formler i OneNote og Word","tags":["matematikk"]}
---


# Formler i OneNote og Word

## Hurtigtaster

### Windows

#### OneNote
`alt + +` ⌥+

#### Word
`alt + shift + 0` ⌥⇧0

#### Powerpoint
`alt + +` ⌥+

### MacOS

#### Onenote
`ctrl + shift + \` ⌃⇧\

#### Word
`ctrl + +` ⌃+

#### PowerPoint
Klarer ikke finne noen tastatursnarvei.

## Nyttige kommandoer og tegn
- Brøkstrek $\frac{a}{b}$: skriv `/` og mellomrom. Det er enklest å lage brøkstreken før du skriver inn telleren og nevneren.
- Gangetegn $\cdot$ : skriv `\cdot`
- Dobbel understrek: `\underbar(\underbar(x=3))`
- Alternativ dobbel understrek: skriv svaret ditt i en parentes, f.eks. `(x=3)` og etterfølg umiddelbart med to stk `\ubar`. Du trenger noen mellomrom for at det skal fomateres pent.
- Eksponenter og indekser (superscript og subscript) $a_0^x$: skriv `a_0^x`
- Uttrykk som eksponent $e^{x+1}$: skriv `a^(x+1)`
- Kvadratrot: `\sqrt(x)`
- Høyere ordens røtter: `\sqrt(5&a)` gir $\sqrt[5]{a}$
- Bestemt integral: `\int_a^b f(x) dx` gir $\int_{a}^{b} f(x) \, dx$
- Sum: `\sum_(i=1)^n f(x_i) \cdot \Delta x` gir $\sum_{i=1}^n f(x_i) \cdot \Delta x$
- Greske bokstaver: `\Delta \Phi \theta \rho \mu` gir $\Delta \Phi \theta \rho \mu$
- Mengdeoperatorer:
	- $\in$ `\in`
	- $\cup$ `\cup`
- Tavle-fet skrift som tallmengder ($\mathbb{R}$): `\DoubleR`

## Smarte tips
- Delt funksjonsuttrykk: `{ \cases(x:=5,x<3@x:=8,x>=3) \close`
- `\sqrt(5&a^2)<space>` gir $\sqrt[5]{a^2}$
- Store parenteser (f.eks. hvis du skal nøste flere parenteser) `\left[ x^2 \right]_0^4` gir $\left[ x^2 \right]_0^4$ og `\left( ((x)^m^n)/(2) \right)^n` gir $\left( \frac{(x^m)^n}{2} \right)^p$
- Equationarray for å skrive over flere linjer: `\eqarray(x+1&=2@1+2+3+y&=z@3/x&=6)<space>`
	- Her angir `&` hvor hvilket tegn man skal justere etter (det er vanlig å bruke `&=` slik at =-tegnene kommer under hverandre.)
	- `@` angir linjeskift.
	- Forhåndsvisning:
	- Forhåndsvisning: $$\begin{align*}
x+1 &= 2\\
1+2+3+y &= z\\
x &= 6
\end{align*}$$
	- Forhåndsvisning:
