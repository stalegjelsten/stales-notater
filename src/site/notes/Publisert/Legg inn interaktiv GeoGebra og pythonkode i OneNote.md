---
{"dg-publish":true,"permalink":"/Publisert/Legg inn interaktiv GeoGebra og pythonkode i OneNote/","title":"Legg inn interaktiv GeoGebra og pythonkode i OneNote","tags":["matematikk","geogebra","python"]}
---

# Legg inn interaktiv GeoGebra og pythonkode i OneNote
Du kan bygge inn interaktive GeoGebra-filer og pythonfiler i OneNote notater.

## GeoGebra

1. Gå til hamburgermenyen i øvre høyre hjørne og `Fil → Save online`.
2. Velg et fornuftig filnavn og la filen være delt. Trykk `Lagre`. *Hvis du ikke er innlogget blir du nå bedt om å logge inn eller lage en GeoGebra konto.*
3. Gå til hamburgermenyen og velg `Fil → Del`
4. Kopier GeoGebra-lenken som kommer fram. Denne skal inneholde `/classic/`
5. Endre på nettadressen slik at `/classic/`-delen blir til `/m/`
6. Lim denne nye nettadressen inn i OneNote. Den vil ha dette formatet: `https://www.geogebra.org/m/zx2s9aft`

Merk at GeoGebra-filene nå er lagret i GeoGebras skyløsning. Det betyr at elevene kun har tilgang til disse GeoGebra-filene så lenge internett er åpent.

## Python
Den eneste typen programmeringsnettside som man kan bygge inn i OneNote (som jeg har funnet) er [https://replit.com/](https://replit.com/). Her må man også lage en brukerkonto først.

1. På *Replit* velger du `Create Repl` og velger programmeringsspråk `Python`
2. Skriv programmet ditt i fila `main.py`
3. Kopier nettadressen, den skal være på formatet `https://replit.com/@brukernavn/NavnPåRepl`
4. Lim inn nettadressen i OneNote

## Bygg inn i itslearning
Hvis man vil ha samme funksjonalitet i notater, gjøremål, innleveringsoppgaver og så videre i itslearning kan du trykke på `Kilde`-knappen i tekstbehandleren i itslearning. Legg til følgende kode der det passer:

```html
<iframe src="ADRESSE_TIL_GEOGEBRA_ELLER_REPL" height="400" width="600" /> 
```

Erstatt teksten som ligger inni `src=""` med lenken fra tidligere
