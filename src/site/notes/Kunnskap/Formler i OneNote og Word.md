---
{"dg-publish":true,"permalink":"/Kunnskap/Formler i OneNote og Word/","title":"Formler i OneNote og Word","tags":["matematikk"]}
---


# Formler i OneNote og Word
Når man skal skrive matematikk i Word så lønner det seg å bruke formeleditoren. Den formaterer tall og variabler på en pen måte, og den er svært rask å bruke når man er blitt vant til tastatursnarveiene og kommandoene. Man åpner formeleditoren ved å velge `Sett inn → Formel` i verktøylinja, eller ved å bruke en [[Kunnskap/Formler i OneNote og Word#Hurtigtaster\|hurtigtast]]. 

I formeleditoren kan du finne de fleste matematiske symbolene i verktøylinja i toppen av vinduet, men det finnes også tastatursnarveier og kommandoer for alle tegnene.

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
- Som standard skrives all skrift i formeleditoren som kursiv. Bruk doble hermetegn `"` rundt tekst for at det skal bli vanlige bokstaver. Spesielt nyttig for enheter, ord, osv.
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

## Hurtigtaster
Disse hurtigtastene setter inn en formel i dokumentet ditt.
### Windows

#### OneNote
<kbd>alt</kbd> <kbd>+</kbd> 

#### Word
<kbd>alt</kbd> <kbd>⇧ Shift</kbd> <kbd>0</kbd> 

#### Powerpoint
<kbd>alt</kbd> <kbd>+</kbd> 

### MacOS

#### Onenote
 <kbd>Ctrl</kbd> <kbd>⇧ Shift</kbd> <kbd>\</kbd>

#### Word
 <kbd>Ctrl</kbd> <kbd>+</kbd>

#### PowerPoint
Klarer ikke finne noen tastatursnarvei.

### Ressurser
[Igal Khitrons nyttige oversikt](https://www.cs.bgu.ac.il/~khitron/Equation%20Editor.pdf)

![[Equation Editor.pdf]]
