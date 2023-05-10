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
- Dobbel understrek: skriv inn svaret in en parentes, f.eks `(x=3)\Ubar` og trykk mellomromtasten to ganger.
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
	- $\cap$ `\cap`
	- $\vee$ `\vee`
	- $\wedge$ `\wedge`
	- $\setminus$ `\setminus`
- Tavle-fet skrift som tallmengder ($\mathbb{R}$): `\DoubleR`

## Smarte tips
- Store parenteser (f.eks. hvis du skal nøste flere parenteser eller sette inn grenser for integrasjon) `\left[ x^2 \right]_0^4` gir $\left[ x^2 \right]_0^4$ og `\left( ((x)^m^n)/(2) \right)^p` gir $\left( \frac{(x^m)^n}{2} \right)^p$
- Delt funksjonsuttrykk: `{ \cases(x:=5,x<3@x:=8,x>=3) \close`
- Equationarray for å skrive over flere linjer: `\eqarray(x+1&=2@1+2+3+y&=z@3/x&=6)<space>`
	- Her angir `&` hvor hvilket tegn man skal justere etter (det er vanlig å bruke `&=` slik at =-tegnene kommer under hverandre.)
	- `@` angir linjeskift.
	- Forhåndsvisning: 

$$\begin{align*}
x+1 &= 2\\
1+2+3+y &= z\\
x &= 6
\end{align*}$$

### Ressurser
[Igal Khitrons nyttige oversikt](https://www.cs.bgu.ac.il/~khitron/Equation%20Editor.pdf)

![[Equation Editor.pdf]]
