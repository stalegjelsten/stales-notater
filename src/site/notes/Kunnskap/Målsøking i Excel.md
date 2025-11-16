---
{"dg-publish":true,"permalink":"/Kunnskap/Målsøking i Excel/","title":"Målsøking i Excel"}
---


### Målsøking i Excel
_Målsøking_ er et verktøy i Excel som brukes når du vet hvilket resultat du ønsker, men ikke hvilken *inngangsverdi* som gir dette resultatet. Excel endrer automatisk på inngangsverdien og prøver seg fram helt til regnearket gir riktig svar.

#### Eksempel med serielån
La oss se på et eksempel hvor vi tar opp et serielån på 50 000 kr som skal betales ned over 5 år med én innbetaling hvert år. Vi kan sette opp en oversikt over nedbetalingene i Excel slik som figuren under viser.

![Oversikt over serielån i Excel](/img/user/Dokumenter/excel-maalsok1.png)

Legg merke til at vi bruker formler i så mange av cellene i tabellen som mulig. Det gjør at regnearket blir *dynamisk*, og at det kan brukes på nytt dersom vi endrer på for eksempel lånebeløpet eller rentefoten.

>[!example] **Eksempel:** Finn rentefoten
>
> Finn hva rentefoten måtte ha vært for at de samlede rentene skulle være 5 500 kr.

1. Trykk i cellen `E12` siden det er denne cellen vi ønsker at skal inneholde målverdien vår, altså 5 500 kr.
2. Åpne verktøyet målsøking ved å søke i søkefeltet på toppen eller ved å navigere til `Data` → `Hva-skjer-hvis-analyse` → `Målsøking`. 
3. Målsøkingsverktøyet trenger 3 parametere. Vi ønsker at celle `E12` skal få verdien 5500. Derfor skriver vi `E12` og `5500` i de to øverste boksene. Se figur &fig:maalsok. I den nederste boksen skriver du cellen som du skal endre på for å finne målverdien. Du kan også trykke direkte på celle C3. Det er ikke nødvendig med `$`-tegn her, men det er heller ikke noe farlig med dem.

![Oppsett av målsøking](/img/user/_resources/maalsok1.png){#fig:maalsok}

![Resultatet fra målsøking](/img/user/_resources/maalsok2.png)