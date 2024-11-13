---
{"dg-publish":true,"permalink":"/Kunnskap/Formeleditoren i OneNote og Word/","title":"Formeleditoren i OneNote og Word","tags":["matematikk"]}
---

# Formeleditoren i OneNote og Word

Når man skal skrive matematikk i Word så lønner det seg å bruke formeleditoren. Den formaterer tall og variabler på en pen måte, og den er svært rask å bruke når man er blitt vant til tastatursnarveiene og kommandoene. Man åpner formeleditoren ved å velge `Sett inn → Formel` i verktøylinja, eller ved å bruke hurtigtastene <kbd>alt</kbd> <kbd>+</kbd> (OneNote) eller <kbd>alt</kbd> <kbd>shift</kbd> <kbd>0</kbd> (Word).

I formeleditoren kan du finne de fleste matematiske symbolene i verktøylinja i toppen av vinduet, men det finnes også tastatursnarveier og kommandoer for alle tegnene.

## Nyttige kommandoer og tegn
- Brøkstrek $\frac{a}{b}$: skriv `/` og mellomrom. Det er enklest å lage brøkstreken før du skriver inn telleren og nevneren.
- Gangetegn $\cdot$ : skriv `\cdot`
- Dobbel understrek: skriv inn svaret i en parentes, f.eks `(x=3)\Ubar` og trykk mellomromtasten to ganger.
- Eksponenter og indekser (superscript og subscript) $a_0^x$: skriv `a_0^x`
- Uttrykk som eksponent $e^{x+1}$: skriv `e^(x+1)` og trykk <kbd>mellomrom</kbd>
- Kvadratrot: `\sqrt(x)`
- Høyere ordens røtter: `\sqrt(5&a)` gir $\sqrt[5]{a}$
- Bestemt integral: `\int_a^b f(x) dx` gir $\int_{a}^{b} f(x) \, dx$
- Sum: `\sum_(i=1)^n f(x_i) \cdot \Delta x` gir $\sum_{i=1}^n f(x_i) \cdot \Delta x$
- Greske bokstaver: `\Delta \Phi \theta \rho \mu` gir $\Delta \Phi \theta \rho \mu$
- Tavle-fet skrift som tallmengder ($\mathbb{R}$): `\doubleR`
- Mengdeoperatorer:
	- $\in$ `\in`
	- $\langle$ og $\rangle$ `\langle` og `\rangle`
	- $\cup$ og $\cap$ `\cup` og `\cap`
	- $\vee$ og $\wedge$ `\vee` og `\wedge`
	- Avanserte operatorer: $\backslash$ `\setminus`, $\mid$ `\mid`, $\forall$ `\forall`, $\therefore$ `\therefore` $$

\clearpage

## Smarte tips
- Som standard settes all skrift i formeleditoren som kursiv. Matematiske variabler og størrelser skal alltid stå i kursiv, mens alle måleenheter og mange matematiske funksjoner skal bruke benytte vanlig skrift. 
	- **Bruk doble hermetegn `"` rundt tekst for at det skal bli vanlige bokstaver.** Spesielt nyttig for enheter, ord, og så videre. 
	- `v=20 "km/h"` og mellomrom gir $v=20 \frac{\text{km}}{\text{t}}$ (riktig)
	- `v=20 km/h` gir $v=20 \frac{km}{h}$ (galt)
- Det finnes to typer visninger av formler: *innebygd* og *frittstående*. 
	- Innebygde formler passer i løpende tekst slik som $f(x)=\frac{1}{x}$, men brøker og lignende kan bli veldig små.
	- Frittstående formler ser penere ut, men de må stå på egne linjer, slik som:
 
$$
f(x)=\frac{1}{x}
$$

![Formeljustering i Word](/img/user/Kunnskap/formeljustering-i-word.png)
- Skrive formler over flere linjer med pen justering, se figuren over.
	- Legg inn den første linja som en frittstående formel. Lag en ny formel direkte nedenfor ved å trykke <kbd>Shift</kbd> <kbd>Enter</kbd> og skrive inn den nye formelen.
	- Trykk så høyre musetast ved punktet som du vil justere etter (som oftest ved likhetstegnet) og `Formeljustering`. Gjenta dette på hver eneste linje.
- Store parenteser (bl.a. nyttig hvis du skal nøste flere parenteser) `\left[ x^2 \right]_0^4` gir $\left[ x^2 \right]_0^4$ og `\left( (x^(m^n))/(2) \right)^p` gir $\left( \frac{(x^{m^n}}{2} \right)^p$
- Delt funksjonsuttrykk: `f(x)=\cases(x^2 & x<3 @ 2x+3 & x>=3)` og mellomrom gir utskriften under (etter å ha lagt til passende mellomrom).
	- `&` bestemmer hvilket tegn linjene skal justeres etter. Her justeres linjene ved mellomrommet mellom funksjonsuttrykket og definisjonsområdet. `@` angir linjeskift.

$$
f(x)=
\begin{dcases}
x^2 &x<3\\
2x+3 &x\geq 3
\end{dcases}
$$
