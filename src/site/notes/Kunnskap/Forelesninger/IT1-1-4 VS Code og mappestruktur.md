---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-1-4 VS Code og mappestruktur/","title":"IT1-1-4 VS Code og mappestruktur","tags":["it1","forelesning"]}
---


# IT1-1-4 VS Code og mappestruktur

## Læringsmål

- Forstå mappestrukturen til programmeringsprosjekter
- Bruke kodesnutter i VS Code for å skrive kode effektivt

---

## Mappestruktur

- Dokumenter er lagret som filer på datamaskinen
- Hver fil ligger befinner seg i en katalog eller mappe
- I programmering bør vi lage en mappe til hvert prosjekt

---

### Oppgave

- Opprett mappen `34-rumpeldunk`
- Åpne mappen i VS Code med `Open folder`
- Opprett filen `index.html` i mappen med VS Code (trykk høyre museknapp i navigasjonsruta på venstre side som heter `34-RUMPELDUNK` og velg `New file`)

---

## VS Code

### Importer profil med innstillinger

Vi skal bruke VS Code gjennom hele året. Du velger selv hvilke fargetemaer og utvidelser du ønsker å bruke.

Importer først profilen med innstillinger som jeg har gjort klar på itslearning.

![h:300](/img/user/_resources/vscode-profile-import.png)

---

### Oppgave

- Gå til [https://vscodethemes.com](https://vscodethemes.com/) og finn et fargetema som du liker.
- Endre fargetema i VS Code. Dette kan f.eks. gjøres ved å åpne kommandopaletten ved å trykke <kbd>Ctrl</kbd> + <kbd>Shift</kbd> + <kbd>P</kbd>
- I kommandopaletten kan du skrive inn `Color theme` eller lignende. Velg enten et innebygget fargetema eller `Browse additional color themes`
- Bruk kommandopaletten til å `Live Preview: Show Preview (Internal Browser)`

---

## Emmet

- Emmet gjør om korte kodesnutter til ekte kode
- `html:5` gir oss skjelettet til et HTML-dokument
- `h1` blir til `<h1></h1>` automatisk
- `ul>li` gir oss et `li`-element inni et `ul`-element
- `ul>li*5` gir oss 5 `li`-elementer inni et `ul`-element

---

### Oppgave

- Lag en nettside (med VS Code og kodesnutter) som inneholder en liste med regler eller utstyr knyttet til Rumpeldunk.
- Finn et bilde av rumpeldunk på internett. Lagre bildet i mappa du laget tidligere.
- Sett inn bildet på nettsiden med `<img src="filnavn.jpg">`
- Du kan justere størrelsen på bildet med attributtene `width` og `height`.
	- Eks: `<img src="bilde.jpg" width="400">`
