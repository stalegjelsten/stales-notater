---
{"dg-publish":true,"permalink":"/Publisert/Installer kart på Garmin-enheter fra Frikart.no/","title":"Installer kart på Garmin-enheter fra Frikart.no","tags":["trening","tek","nerding","Instruksjoner"]}
---


# Installer kart på Garmin-enheter fra Frikart.no
[Frikart.no](http://frikart.no/) er en tjeneste som tilbyr gratis kart til Garmin GPS-enheter basert på [OpenStreetMap](https://OpenStreetMap.org). Her forklarer jeg hvordan man kan laste ned et topografisk kart med høydekurver og alle stier.

## Framgangsmåte
### Last ned og gjør klar kart
1. Gå til [frikart.no](http://frikart.no/)
2. Velg *Maps for Garmin GPS*
3. Trykk på Norge
4. Velg kartet *Topo Summer* og trykk på lenken *File for GPS* for å laste ned kartet (omtrent 1,5 GB)
5. Når nedlastingen er ferdig pakker du ut `.zip`-fila slik at du får en fil som `gmapsupp.img`

### Overføre kart til Garmin-enhet på Windows
1. Koble Garmin-enheten til datamaskinen din med ladekabelen. Garmin-enheten skal dukke opp som en egen enhet under *Min Datamaskin*. 
2. Flytt den nye `gmapsupp.img`-fila til mappen `GARMIN` som ligger på Garmin-enheten. Hvis du har en `gmapsupp.img` fra tidligere så er det ikke farlig å erstatte denne.

Den belgiske bloggen [No Place Like Outside](https://noplacelikeoutside.be/how-to-install-free-maps-on-garmin-gps-openstreetmap/) har en fin demonstrasjon av hvordan dette gjøres i Windows.

### Overføre kart til Garmin-enhet på macOS
For å kunne overføre filer til en Garmin-enhet på macOS er du nødt til å installere en egen app. 

1. Gå til <https://openmtp.ganeshrvel.com/> og last ned OpenMTP
2. Installer OpenMTP
3. Koble Garmin-enheten til Macen med en ladekabel. 
4. Åpne OpenMTP. Godta standardinnstillingene.
5. Åpne mappen `GARMIN` på Garmin-enheten på høyre siden av OpenMTP-vinduet.
7. Flytt `gmapsupp.img` over til GPS-enheten (i skjermbildet nedenfor ser du at jeg har navigert til mappen GARMIN)
8. Hvis du har en `gmapsupp.img` fra tidligere så er det ikke farlig å erstatte denne.

![](/img/user/_resources/openmtp.png)
### Aktivere kartlaget på Garmin-enheten
Disse instruksjonene gjelder for Garmin Fenix klokker. Dersom du har en annen type enhet kan du søke på «Garmin (navn på enhet) enable maps» for å finne instruksjoner.

1. Koble Garmin-enheten fra PC-en.
2. Trykk på start-knappen `▲` på klokka
3. Gå til *Kart* eller *Maps*
4. Trykk `MENU`-knappen for å åpne innstillinger
5. Gå til *Kart-innst.* eller *Map settings*
6. Velg *Kart* → *Konfigurer kart* eller *Map* → *Configure Maps*
7. Bla ned og aktiver *OpenStreetMap* kartet, som vist i skjermbildet under.
8. Det er mulig å lage velge egne kartlag for hver aktivitetsprofil. Dersom kartet ikke vises riktig så kan du sjekke om det er aktivert etter å ha valgt riktig idrett/aktivitesprofil.
 
![](/img/user/_resources/OpenStreetMap-garmin.png)

## Ressurser
- https://noplacelikeoutside.be/how-to-install-free-maps-on-garmin-gps-openstreetmap/
