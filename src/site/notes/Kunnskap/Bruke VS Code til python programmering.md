---
{"dg-publish":true,"permalink":"/Kunnskap/Bruke VS Code til python programmering/","title":"Bruke VS Code til python programmering","tags":["it","it1"]}
---


# Bruke VS Code til python programmering
I matematikkfagene (og kanskje andre realfag) skal du programmere i programmeringsspråket Python. Du har kanskje brukt programmet [Mu](https://codewith.mu/) til å skrive Pythonkode fram til nå. Det er et enkelt og greit program, men det kan være fordelaktig å heller bruke et program som [Visual Studio Code](https://code.visualstudio.com/). VS Code har følgende fordeler:

- *IntelliSense* fullfører koden din for deg
- De ulike delene av koden din blir farget for å gi bedre oversikt
- En mye bedre *debugger* for å finne feil i koden
- Du kan skrive Pythonkode i [Jupyter notebooks](https://jupyter.org/). Dette lar deg skrive tekst, matematikk, HTML-kode og Pythonkode i samme dokument. Det lar deg også dele opp koden i ulike blokker som kan kjøres uavhengig av hverandre.

## Oppsett
For å kunne bruke Python i VS Code så må du først installere Python på datamaskinen din. Da du installerte Mu så ble det allerede installert en Python-versjon, men denne er ofte utdatert. 

Hvis du ønsker en pythoninstallasjon som har alle nødvendige pakker for realfag (+ veldig mange andre) så anbefaler jeg at du velger løsningen fra *Anaconda*. Hvis du går P-matte så fungerer det nok veldig fint å installere Python fra *Microsoft Store*.

### Anaconda
Anaconda er en samling av Python pluss mange ekstra pakker som gir ekstra funksjoner til Python, blant annet innen statistikk, sannsynlighet, databehandling, tegning av grafer og så videre. Selv om denne løsningen tar mer lagringsplass og mer tid, så er det denne jeg anbefaler siden alt du trenger kommer ferdig installert.

For å installere Anaconda går du til [anaconda.com/download](https://www.anaconda.com/download) og trykker på `Download`-knappen. Du er nødt til å dobbeltklikke på fila og installere den på egen datamaskin. Dette tar en stund siden Anaconda er et stort program.

>[!tip] Alternativ installasjonsmetode
>I Windows kan du også åpne en Terminal (for eksempel PowerShell) og kjøre kommandoen `winget install Anaconda.Anaconda3 -s winget`

### Python fra Microsoft store
Åpne *Microsoft Store* på datamaskinen og søk etter *Python*. Installer den nyeste versjonen. I 2023 er Python 3.11 den nyeste versjonen som er tilgjengelig i Microsoft Store.

### Oppsett av Visual Studio Code
1. Åpne Visual Studio Code og aktiver IT1-profilen (hvis dette ikke ble gjort automatisk).
2. Velg *Open folder*. Velg en mappe som inneholder pythonfiler.
3. Åpne en av pythonfilene. 
4. Hvis teksten *Select interpreter* kommer opp, så velger du den linja som enten inneholder teksten `conda` (hvis du installerte Anaconda) eller `(microsoft store)`. I mitt tilfelle heter den `★ Python 3.11.5 64-bit (microsoft store)`.
5. Hvis ikke *Select interpreter* dukker opp så kan du skrive inn kommandoen `Python: Select interpreter` i kommandolinja (<kbd>Ctrl</kbd> <kbd>↑Shift</kbd> <kbd>P</kbd>)

Nå skal du være klar til å bruke Python i Visual Studio code. 

## Kjøre pythonfil i VS coce
For å kjøre pythonkode så er du nødt til å lagre fila (<kbd>Ctrl</kbd> <kbd>S</kbd>). Trykk deretter på play-symbolet (▷) i øvre høyre del av skjermen.
