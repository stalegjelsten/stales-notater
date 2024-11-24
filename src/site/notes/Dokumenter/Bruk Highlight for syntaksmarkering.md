---
{"dg-publish":true,"permalink":"/Dokumenter/Bruk Highlight for syntaksmarkering/","title":"Bruk Highlight for syntaksmarkering","tags":["lærer","programmering","python"]}
---


# Bruk Highlight for syntaksmarkering
Kode ser mye bedre ut dersom det brukes synktaksmarkering, (englesk: *syntax highlighting*), altså ulike farger for variabelnavn, funksjoner, strenger og så videre.

Hvis man skal lime inn kode i et Officeprogram eller itslearning så kan man få syntaksmarkering ved hjelp av programmet [Highlight](http://www.andre-simon.de/doku/highlight/en/highlight.php).

## Oppsett

- Last ned [Highlight](http://www.andre-simon.de/zip/download.php). 
	- Velg en av`exe`-filene for Windows
	- Velg Mac OS GUI versjonen for macOS
- Åpne fila. Hvis du bruker Mac må du sannsynligvis gå inn i Innstillinger (Systemvalg) → Personvern og sikkerhet → *macOS kan ikke bekrefte utvikleren av highlight-gui*, velg Åpne likevel.
- Velg programmeringsspråk ved `Select syntax`, for eksempel python.
- Under `General` så bruker jeg formatet `RTF` som passer fint for å lime inn i Officeprogrammer.
- Under `RTF-options` så har jeg fjernet avkrysningen ved `Set page color`. Da slipper jeg å dra med bakgrunnsfargen når jeg limer inn koden.
- Under `Formatting` så liker jeg å bruke et lyst tema: `vim earendel`.

## Bruk
Jeg pleier å markere all koden i Mu og kopiere denne (<kbd>ctrl</kbd> <kbd>A</kbd> for å merke koden og <kbd>ctrl</kbd> <kbd>C</kbd> for å kopiere den). Deretter trykker jeg på knappen `Paste, convert and copy` i Highlight. Da legger den ferdige formaterte koden seg på utklippstavlen, og du kan lime den inn i et annet program.

>[!tip] Hva gjør jeg når OneNote ikke vil lime inn koden?
>OneNote kan være litt vrien med tanke på hva slags tekst den ønsker å lime inn. Dersom du ikke får limt inn koden i OneNote så kan du:
>
>1. Lime inn koden i et tomt Word-dokument først
>2. Kopiere koden fra Word-dokumentet
>3. Lime inn koden i OneNote
