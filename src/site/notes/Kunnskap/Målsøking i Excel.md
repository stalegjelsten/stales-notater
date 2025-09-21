---
{"dg-publish":true,"permalink":"/Kunnskap/Målsøking i Excel/","title":"Målsøking i Excel"}
---


# Målsøking i Excel
Målsøking er et verktøy i Microsoft Excel som lar oss definere en *målverdi*, og som endrer på én celle slik at regnearket gir oss denne målverdien.

## Eksempel med serielån
La oss se på et eksempel hvor vi tar opp et serielån på 50 000 kr som skal betales ned over 5 år med én innbetaling hvert år. Vi kan sette opp en oversikt over nedbetalingene i Excel slik som figuren under viser.

![Pasted image 20250905141524.png](/img/user/_resources/Pasted%20image%2020250905141524.png)

Legg merke til at vi bruker formler i så mange av cellene i tabellen som mulig. Det gjør at regnearket blir *dynamisk*, og at det kan brukes på nytt dersom vi endrer på for eksempel lånebeløpet eller rentefoten.

Hvis vi nå får i oppgave å finne ut hva rentefoten måtte ha vært for at de samlede rentene skulle være 5 500 kr, så kan vi bruke målsøking.

1. Trykk i cellen `E12` siden det er denne cellen vi ønsker at skal inneholde målverdien vår, altså 5 500 kr.
2. Åpne verktøyet målsøking ved å søke i søkefeltet på toppen eller ved å navigere til `Data` → `Hva-skjer-hvis-analyse` → `Målsøking`. Se figuren.
3. Målsøkingsverktøyet trenger 3 parametere. Vi ønsker at celle `E12` skal få verdien 5500. Derfor skriver vi `E12` og `5500` i de to øverste boksene. I den nederste boksen skriver du cellen som du skal endre på for å finne målverdien. Du kan også trykke direkte på celle C3. Det er ikke nødvendig med `$`-tegn her, men det er heller ikke noe farlig med dem.

![Pasted image 20250905142247.png](/img/user/_resources/Pasted%20image%2020250905142247.png)

![Pasted image 20250905143001.png](/img/user/_resources/Pasted%20image%2020250905143001.png)