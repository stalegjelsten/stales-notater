---
{"dg-publish":true,"permalink":"/Orientering/LiveRes for etiming/","title":"LiveRes for etiming","tags":["etiming","orientering"]}
---


# LiveRes for etiming
LiveRes fungerer som liveresultater til [[Orientering/eTiming\|eTiming]]. Kristiansand OK har i 2023 lisens på programmet. Kontakt Ståle for brukernavn/passord for innlogging.

LiveRes består av en klient (et program som kjører på samme datamaskin som [[Orientering/eTiming\|eTiming]]) og en webserver. Du må opprette løpet hos webserveren før du kan bruke tjenesten.

## Oppsett hos LiveRes (webserver)
- Gå til <https://liveres.live/adm/>
- Velg `Create new competition` fra toppmenyen
- Skriv inn navn, dato og arrangørklubb. Jeg anbefaler at du er nøye med at dette blir likt som i Eventor og som i eTiming.
- Noter deg `Competition ID` som du blir tildelt. Du trenger ikke endre på noen av innstillingene (hvis `Show ecard split times` ikke er avmerket så bør du merke av denne. Det gjør at folk kan sjekke strekktider live).

## Oppsett av klient
- Last ned nyeste versjon av klienten fra <https://github.com/palkitt/liveresults/releases.> Velg den nyeste fila som heter LiveResClient_dato.zip
- Du trenger også en config-fil. Kontakt Ståle for å få tilsendt denne
- Inne i programmet så velger du eTiming som tidtakingsprogram og velger databasefila til arrangementet
- Husk å skrive inn riktig `Competition ID` slik at resultatene sendes til riktig side
- Klienten laster nå opp nye resultater så fort den merker endringer i databasen.

[Kildekode](https://github.com/palkitt/liveresults)
[Webgrensesnitt](https://liveres.live/adm/)
