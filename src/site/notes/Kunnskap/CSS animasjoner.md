---
{"dg-publish":true,"permalink":"/Kunnskap/CSS animasjoner/","title":"CSS animasjoner","tags":["css","it1","uferdig"]}
---


# CSS animasjoner

Animasjoner i [[Kunnskap/CSS\|CSS]] kan gjøres på følgende måte 👇
```css
transition: all 0.5s ease-in-out;
animation: myAnim 0.5s;

@keyframes myAnim {
	0% {transform: scale(1)}
	50% {transform: scale(1.4)}
	100% {transform: scale(1)}
}
``` 

Her har vi opprettet en animasjon med 3 *keyframes*. Ved starten av animasjonen skal størrelsen på elementet være 100 % (1). Halvveis i animasjonen skal størrelsen være 140 % (1,4). Ved slutten av animasjonen skal størrelsen være 100 % igjen.

Vi ser at animasjonen skal foregå over 0,5 sekunder, og at vi har gitt tidsfunksjonen `ease-in-out`. Dette gjør at animasjonen får en myk start og slutt. En slik type animasjon ser behagelig og naturlig ut.

## Enkle animasjon på :hover
Hvis du vil animere et [[Kunnskap/HTML\|HTML]] element når [[Kunnskap/CSS pseudoklasser#Bruk hover for å endre på elementer når man holder musen over dem\|musepekeren holdes over elementet]] kan du enkelt bruke:
```css
h1 {
	transition: all 0.1 ease-in-out;
	transform: scale(1);
}
h1:hover {
	transform: scale(1.2);
}
```

## Animasjoner av JavaScript states
Man kan animere et element ut fra en variabel i [[Javascript\|Javascript]] ved å definere ulike klasser i CSS og sette inn.

>[!todo] Fullfør avsnittet om animasjoner av javascript states
