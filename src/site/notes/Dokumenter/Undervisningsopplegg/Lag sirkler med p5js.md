---
{"dg-publish":true,"permalink":"/Dokumenter/Undervisningsopplegg/Lag sirkler med p5js/","tags":["prøver"]}
---


![](/img/user/_resources/sirkler-logo.png)

# Steg 1: Vi tegner sirkler
Matematikere elsker sirkler. De er symmetriske og de har det største arealet i forhold til sin periferi av alle former. 

La oss tegne noen sirkler med kode på [p5js.org](https://p5js.org).

```js{.js caption="Kode for å tegne sirkler" #code:steg1}
// Det som står etter // er kommentarer. Kommentarer har også gullfarge på dette arket.
// Kommentarene er ikke en del av koden, og du trenger ikke skrive dem inn.

function setup() {
  // Alt som står inni setup skjer når vi starter programmet
  // createCanvas setter bredden og høyden til lerretet vi tegner på 
  createCanvas(400, 400) 
  // background setter bakgrunnsfargen. 0 er svart og 255 er hvitt
  background(20)
}

function draw() {
  // Alt som står inni draw skjer 60 ganger per sekund
  if (mouseIsPressed) {
    // circle lager en sirkel med størrelse 50 der hvor musepekeren befinner seg
    circle(mouseX, mouseY, 50)
  }
}
```

>[!tip] Oppgave 1
>
>
>a) Bruk musepekeren til å tegne sirkler. Klarer du å få det til å se ut som om bildet ditt har dybde?
>b) Lag et bilde med sirklene og få de som du sitter ved siden av til å gjette hva du har tegnet. Gjett også hva de andre har tegnet.
>c) Endre på verdien av `background(20)` til du er fornøyd.
>d) Endre på størrelsen av sirklene til du er fornøyd. *Hint: se kommentarene i koden*

\clearpage

# Steg 2: Sirkler med tyngdekraft
Fysikere elsker legemer som beveger seg, så la oss få sirklene våre til å falle mot bakken.

For å få til dette så må vi både lagre posisjonen og farten til hver eneste sirkel. Det er litt komplisert å programmere, så dere må bare godta det vi skriver foreløpig.

## Steg 2.1: Sirkelklasser
Vi trenger å fortelle datamaskinen hvilke egenskaper en sirkel skal ha. Det kan vi gjøre ved å definere en klasse som vi kaller `Sirkel`. Legg til koden i kodesnutt &code:klasse i toppen av programmet ditt.

```js{.js caption="Sirkelklasse" #code:klasse}
class Sirkel {
  // Alt som står inni constructor skjer når vi lager en ny sirkel
  
  constructor() {
    this.x = mouseX // x-posisjonen til sirkelen bestemmes av musepekeren
    this.y = mouseY // x-posisjonen til sirkelen bestemmes av musepekeren
    this.s = 20     // Diameteren til sirkelen
    this.fart = 0   // Farten til sirkelen
    this.farge = color(310, 100, 100)  // Gir farge til hver sirkel
  }

  // Vi lager funksjonen tegn for tegne sirkelen på lerretet
  tegn() {
	  fill(this.farge)                // Sirkelens farge
	  circle(this.x, this.y, this.s)  // Tegner sirkelen
  }
}
```

## Steg 2.2: Lage liste
Vi har lyst til å opprette mange sirkler, og vi trenger et sted å lagre informasjonen om alle disse sirklene, i tillegg må vi legge til en tyngdekraft. Tyngdekraften virker som en akselerasjon som drar hver sirkel ned mot bunnen av lerretet. Legg til kodesnutt &code:liste i toppen av programmet ditt.

```js{.js caption="Tyngdekraft og liste med sirkler" #code:liste}
const a = 0.05   // Tyngdekraft = 0.05
let sirkler = [] // En tom liste med plass til sirklene våre
```

\clearpage

## Steg 2.3: Legge sirkler inn i lista
Nå skal vi legge inn nye sirkler i lista vår `sirkler` når vi trykker på musa. Endre på funksjonen `setup` slik at den blir som kodesnutt &code:setup2. Endre på `draw` slik at den blir som kodesnutt &code:draw2.

```{.js caption="Ny setup-kode" #code:setup2}
function setup() {
  createCanvas(400, 400)
  // HSB gjør at vi kan velge farge ved å sette (Fargenyanse, Metning, Lysstyrke)
  colorMode(HSB)
}
```

```js{.js caption="Ny draw-kode" #code:draw2}
function draw() {
  background(20)
  if (mouseIsPressed) {
    sirkler.push(new Sirkel()) // Legg til en ny Sirkel inn i lista
  }
  for (let i = 0; i < sirkler.length; i++) {
    sirkler[i].tegn() // Fancy kode som tegner alle sirklene våre
  }

  if (sirkler.length > 600) {
    sirkler.shift() // Hvis vi har mer enn 600 sirkler så sletter vi den eldste 
  }
}
```

<!--
>[!warning] Fungerer ikke programmet?
>
>Du finner hele programmet (fram til nå) på nest siste side i kodesnutt &code:steg23. 
>
>Programmet ligger også i tekstfilen `program-etter-steg-2-3` på skrivebordet på PC-en din, slik at du kan kopiere det over.-->

>[!tip] Oppgave 2
>
>Bruk musepekeren til å tegne sirkler. *Hvis ikke koden fungerer så finner du hele programmet på nest siste side i kodesnutt &code:steg23, og i fila `program-etter-steg-2-3` på skrivebordet på PC-en.*
>
>a) Endre på størrelsen av sirklene til du finner en størrelse du er fornøyd med
>
>Du kan endre på fargene ved å endre linja `this.color = color(310, 100, 100)`. Det første tallet (310) styrer fargenyansen, og det er et tall mellom 0–360. Det andre tallet styrer metningen av fargen (hvor intens den er) ved å bruke et tall mellom 0–100. Det tredje tallet styrer lysstyrken til fargen og er et tall mellom 0–100.
>
>b) Prøv deg fram ved å endre på verdiene til `color` og finn noe du er fornøyd med.
>c) Endre på fargene ved å sette `this.color = color(frameCount % 360, 100, 100)`. Du kan bytte ut 100 og 100 med andre verdier hvis du ønsker.

\clearpage

## Steg 2.4: Få sirklene til å falle
Nå skal vi bruke matematikk til å beregne to størrelser:

1. Hvor fort hver sirkel faller mot bakken
2. Hvor hver sirkel befinner seg

Vi skal beregne både denne nye farten og den nye posisjon veldig ofte. Når vi tegner sirklene på skjermen 60 ganger per sekund, så ser det ut som at sirklene flytter på seg.

Det vi gjør nå er egentlig å bruke *Eulers metode* for å løse differensiallikninger – dere gjør superavansert universitetsmatematikk allerede nå ved hjelp av en datamaskin.

Legg til følgende kode inni klassen til `Sirkel`:

```js{.js caption="Beregner ny fart og posisjon til sirkelen ved hjelp av Eulers metode" #code:update}
  update() {
    this.fart = this.fart + a    // Legg til akselerasjonen på farten til sirkelen
    this.y = this.y + this.fart  // Legg til farten på y-posisjonen til sirkelen
  }
```

Endre på `for`-løkka i `draw` slik at den blir som dette:

```js{.js caption="Ferdig for-løkke" #code:for}
  for (let i = 0; i < sirkler.length; i++) {
    sirkler[i].update() // Regner ut ny fart og posisjon til hver sirkel
    sirkler[i].tegn()   // Tegner hver sirkel på skjermen i den nye posisjonen
  }
```

>[!warning] Fungerer ikke programmet?
>
>Hvis du har problemer med å få programmet til å fungere så finner du det ferdige programmet på siste side i kodesnutt &code:ferdig. 
>
>Programmet ligger også i tekstfilen `ferdig-program` på skrivebordet på PC-en din, slik at du kan kopiere det over.

>[!tip] Oppgave 3
>
>a) Endre på verdien av `const a = 0.05`. Hva skjer? Velg en verdi dere synes er passelig.
>b) Endre på verdien av `this.fart = 0` til å bli `this.fart = -2`. Hva skjer?
>c) Kan dere få sirklene til å "falle" oppover?
>d) Kan dere få sirklene til å falle mot høyre, venstre eller på skrå?

\clearpage
```js{.js caption="Program etter steg 2.3" #code:steg23}
const a = 0.05
let sirkler = []

class Sirkel {
  constructor() {
    this.x = mouseX
    this.y = mouseY
    this.s = 50
    this.fart = 0;
    this.farge = color(310, 100, 100)
  }
  
  tegn() {
    fill(this.farge)
    circle(this.x, this.y, this.s)
  }
}

function setup() {
  createCanvas(400, 400)
  colorMode(HSB)
}

function draw() {
  background(20)
  if (mouseIsPressed) {
    sirkler.push(new Sirkel())
  }
  for (let i = 0; i < sirkler.length; i++) {
    sirkler[i].tegn()
  }
  
  if (sirkler.length > 600) {
    sirkler.shift();
  }
}
```

\clearpage

```js{.js caption="Ferdig program" #code:ferdig}
const a = 0.05     // Akselerasjon (tyngdekraft)
let sirkler = []   // Tom liste til å lagre sirklene

class Sirkel {     // Klassen Sirkel definerer egenskapene til hver sirkel
  constructor() {
    this.x = mouseX // x-posisjonen til sirkelen bestemmes av musepekeren
    this.y = mouseY // x-posisjonen til sirkelen bestemmes av musepekeren
    this.s = 20     // Diameteren til sirkelen
    this.fart = 0   // Farten til sirkelen
    this.farge = color(frameCount % 360, 100, 100) // Gir ulik farge til hver sirkel
  }
  
  tegn() {                            // Denne funksjonen tegner sirkelen
    fill(this.farge)                  // Sirkelen skal fylles med sin egen farge
    circle(this.x, this.y, this.s)    // Sirkelen tegnes
  }
  
  update() {                      // Denne funksjonen beregner ny fart og posisjon
    this.fart = this.fart + a     // nyFart = gammelFart + akselerasjon * tid
    this.y = this.y + this.fart   // nyPosisjon = gammelPosisjon + fart * tid
  }
}

function setup() {
  createCanvas(400, 400)  // Oppretter 400 x 400 punkters lerret
  colorMode(HSB)          // Farger er bestemt av fargenyanse, metning og lysstyrke
}

function draw() {
  background(20)          // Tegner bakgrunnen med mørk gråfarge
  if (mouseIsPressed) {   // Alt inni if-setningen skjer bare når museknappen er trykket ned
    sirkler.push(new Sirkel())  // Vi oppretter en ny sirkel og legger inn i lista sirkler
  }
  
  for (let i = 0; i < sirkler.length; i++) { // Vi går gjennom alle sirklene
    sirkler[i].update()          // Vi oppdaterer fart og posisjon til hver sirkel
    sirkler[i].tegn()            // Vi tegner hver sirkel på lerretet
  }
  
  if (sirkler.length > 600) {
    sirkler.shift();  // Hvis det er over 600 sirkler så sletter vi den første for (ellers blir datamaskinen fort overbelastet)
  }
}
```
