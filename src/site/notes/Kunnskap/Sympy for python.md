---
{"dg-publish":true,"permalink":"/Kunnskap/Sympy for python/","title":"Sympy for python","tags":["python","matematikk","programmering"]}
---


# Sympy for python
`sympy` er et bibliotek for symbolsk eller analytisk matematikk i [[Kunnskap/Python\|Python]]. Det kan på noen måter sammenlignes med `CAS` i [[Kunnskap/GeoGebra\|GeoGebra]].

## Enkel bruk av sympy
```python
import sympy as sp

x = sp.Symbol("x")
uttrykk = x**2 + 2*x
integral = sp.integrate(uttrykk)

print(f"La f(x) = {uttrykk}. Da er {integral} en antiderivert av f")
print(f"f(3) = {uttrykk.subs(x, 3)}")
```

La oss gå gjennom koden ovenfor 
- Vi importerer `sympy` og velger `sp` som kortnavn.
- Vi oppretter en matematisk variabel med `Symbol` fra `sp` (husk at dette er kortnavnet for sympy). Denne matematiske variabelen tilordner vi til pythonvariabelen `x` med `x = `.
- Vi definerer et uttrykk $x^{2}+2x$
- Vi integrerer uttrykket med `sp.integrate()` og tilordner resultatet til variabelen `integral`
- Vi skriver ut både uttrykket og den integrerte
- I siste linje regner vi ut $f(3)$ ved å sette inn `3` istedenfor `x` ved hjelp av metoden `subs()`. 

## Å bestemme mange funksjonsverdier
Vi kan bestemme funksjonsverdien til $f(3)$ i `sympy` med `uttrykk.subs(x, 3)`, men det er ikke mulig å få tilbake mer enn en funksjonsverdi på denne måten. Vi *kan* lage en for-løkke som gir tilbake mange funksjonsverdier, men dette er veldig lite effektivt og gjør koden vår svært langsom.

I eksempelet under så gjør vi om det symbolske uttrykket $x^{2}+2x$ til en funksjon `f(x)` som bruker numpy til å bestemme funksjonsverdiene numerisk. Vi oppretter deretter et array med 400 $x$-verdier for $x\in [0,4]$ og plotter $x$-verdiene mot $f(x)$.

```python
import sympy as sp
import numpy as np
import matplotlib.pyplot as plt

x = sp.Symbol("x")
uttrykk = x**2 + 2*x
f = sp.lambdify(x, uttrykk, "numpy")

x_verdier = np.linspace(0,4,200)
fig, ax = plt.subplots()
ax.plot(x_verdier, f(x_verdier))
plt.show()
```

## Gjøre om strings til sympy-uttrykk
Man kan ta en hvilken som helst tekststreng og gjøre den om til et `sympy`-uttrykk med `sympify`. Nedenfor vises et eksempel som tar inn tekststreng fra brukeren og lager et `sympy`-uttrykk fra denne.

```python
import sympy as sp
mystring = input("f(x) = ")
uttrykk = sp.sympify(mystring)
integral = sp.integrate(uttrykk)
print(f"F(x) = {integral} er en antiderivert til f(x) = {uttrykk}")
```

## Forklaring av funksjoner i sympy

### Solve brukes for å løse likninger
Den enkleste måten å løse likninger på er å bruke `sp.solve()`, men vi må først definere en likning med `sp.Eq()`.

I eksempelet nedenfor så definerer vi variabelen `x`, funksjonen $f(x)=3x^{2}+2x$ og skal løse likningen $\int_{0}^{a} (3x^{2}+2x) \, dx=36$

For å unngå å få [[Komplekse tall\|komplekse løsninger]] så gir vi `real=True` som parameter når vi definerer symbolet `x`. Dette gjør at vi kun får løsninger hvor $x\in \mathbb{R}$.

```python
import sympy as sp
x = sp.Symbol("x", real=True)
uttrykk = 3*x**2 + 2*x
integral = sp.integrate(uttrykk)
likning = sp.Eq(integral, 36)
losning = sp.solve(likning)
print(f"{integral} = 36 når x = {losning}")
```