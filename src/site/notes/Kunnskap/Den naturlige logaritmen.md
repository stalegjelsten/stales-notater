---
{"dg-publish":true,"permalink":"/Kunnskap/Den naturlige logaritmen/","title":"Den naturlige logaritmen","tags":["matematikk","s2"]}
---


# Den naturlige logaritmen
Den naturlige logaritmen $\ln x$ er definert på følgende måte:

>[!important] Definisjon av $\ln x$
Den naturlige logaritmen $\ln x$ er den inverse funksjonen til $e^{x}$ slik at 
> $$ e^{\ln x}=x $$
> 
> Siden $e^{x}>0$ vil også $e^{\ln x}>0$. Ut fra likheten over så ser vi at $x>0$.
> 
> Definisjonsmengden er dermed alle positive tall, $x \in \mathbb{R} \mid x > 0$.
> Verdimengden er alle reelle tall $\mathbb{R}$.

```mathpad
%$1:=[ln*x]
plot(log(x), [-1,5], [-4,2])==?
```

## Den deriverte av ln x
Den deriverte av $\ln x$ er $\frac{1}{x}$. 

>[!important] Beviset for $(\ln x)'=\frac{1}{x}$
>Vi vet at
>$$
>e^{\ln x}=x
>$$
>
>For å bevise $(\ln x)'=\frac{1}{x}$ så deriverer vi hver side av likningen ovenfor og sammenligner svarene. Hvis vi deriverer den høyre siden av får vi at 
>$$
>(x)' = 1
>$$
>Vi kan også forsøke å derivere den venstre siden av likningen ved hjelp av [[kjerneregelen\|kjerneregelen]]. Vi setter da $u=\ln x$ og får
>$$
>(e^{\ln x})' = (e^{u})'\cdot u'=e^{u}\cdot (\ln x)'=\underbrace{ e^{\ln x} }_{ =x }\cdot (\ln x)'=x\cdot (\ln x)'
>$$
>
>Foreløpig kommer vi ikke lengre, siden vi enda ikke har bevist hva den deriverte av $\ln x$ er. Her kommer derfor den geniale ideen inn – vi sammenligner resultatene av derivasjonene.
>
>Siden vi vet at $e^{\ln x}=x$ så må $(e^{\ln x})'=x'$. Derfor må også:
>$$
\begin{aligned}
(e^{\ln x})'&=x'\\
x\cdot (\ln x)' &= 1 \\
(\ln x)' &= \frac{1}{x} && {\mathbb{Q.E.D.}} \\
\end{aligned}
$$
