---
{"dg-publish":true,"permalink":"/Kunnskap/Halveringstid/","title":"Halveringstid","tags":["fysikk","naturfag"]}
---


# Halveringstid
Halveringstid er tiden det tar før halvparten av et [[Kunnskap/Radioaktivitet\|radioaktivt]] stoff er blitt omdannet. Omdanningshastigheten til et radioaktivt stoff er avhengig av hvor mye radioaktivt stoff vi har. Derfor kan halveringstiden framstilles som en eksponentialfunksjon som nærmer seg null når tiden går. Et kjent eksempel på halveringstid er karbon-14 som har en halveringstid på 5730 år. Hvis vi ønsker å datere (finne ut hvor gammelt) biologisk materiale, så kan vi utnytte at vi kjenner halveringstiden til Karbon-14.

Hvis vi har mengden $N_0$ av et stoff ved tiden $t_0$ og halveringstiden til stoffet er $t_{\frac{1}{2}}$, så kan vi uttrykke mengden stoff $N$ som er igjen etter tiden $t$ ved formelen:

$$N(t) = N_{0}\cdot \left(\frac{1}{2} \right)^{\frac{t}{t_{\textstyle{1 \over 2}}}}$$

Eksempelet med karbon-14 blir da

$$N(t) = N_{0}\cdot \left(\frac{1}{2} \right)^{\frac{t}{5730}}$$

## Eksempel med Kobolt-60
![](https://chem.libretexts.org/@api/deki/files/63554/CNX_Chem_21_03_HalfLife.jpg?revision=1&size=bestfit&width=602&height=367)
Figurkilde: OpenStax CC-BY 4.0
Kobolt-60 ($\ce{^60_27Co}$) har halveringstid 5,27 år. Det er en radioaktiv isotop som sender ut [[Kunnskap/Betastråling\|betastråling]] ($\beta$), slik at stoffet omdannes til Nikkel-60. 

Hvis vi starter med 10 g Kobolt-60 så vil vi etter 5,27 år ha 5 g Kobolt-60 pluss 5 g Nikkel-60 (minus vekten av elektronene som er sendt ut som betastråling, men dette er neglisjerbart. Husk at et proton har 2000 ganger større masse enn et elektron).

Etter $2\cdot 5{,}27$ år (altså 10,54 år) vil det kun være 2,5 g Kobolt-60 og 7,5 g Nikkel-60.

Vi kan sjekke at dette stemmer med formelen vår. $N_0=10$, $t=10{,}54$, $t_\frac{1}{2}=5{,}27$ gir:

$$N(10.54)=10\cdot(\frac{1}{2})^{\frac{10.54}{5.27}} = 10\cdot(\frac{1}{2})^{2}=10\cdot \frac{1}{4}=2.5$$

## Karbon-14 datering
Datering med karbon-14 utnytter at vi vet at halveringstiden til karbon-14 er 5730 år. Karbon-14 er et radioaktivt stoff som sender ut [[Kunnskap/Betastråling\|Betastråling]] og omdannes til Nitrogen-14. 

Det er omtrent $10^{12}$ vanlige karbon-12 isotoper i lufta per karbon-14 isotop. Så lenge vi lever så vil vi også ha ca $\frac{1}{10^{12}}$ karbon-14 isotoper i kroppen, men når vi dør vil vi ikke lenger ta opp nytt karbon-14. Mengden karbon-14 kommer derfor til å minke, og vi kan måle radioaktiviteten med en geigerteller. Vi kan ut fra disse målingene beregne sist gang organismen vi ser på var i live.

## Strålingsaktivitet
Strålingsaktivitet er hvor mye stråling et radioaktivt stoff sender ut per tidsenhet. 
Strålingsaktivitet til et radioaktivt stoff er proporsjonal med mengden radioaktivt stoff. Dermed vil halveringstiden også si noe om hvor strålingsaktiviteten. 
- Et stoff med kort halveringstid vil omdanne stoff fort, og vil derfor ha høy strålingsaktivitet. 
- Et stoff med lang halveringstid vil ha lav strålingsaktivitet. 

---

## Lisenser
Figur av halveringstid by OpenStax. [CC-BY 4.0](https://creativecommons.org/licenses/by/4.0/) 
![Creative Commons License](https://i.creativecommons.org/l/by/4.0/80x15.png)
