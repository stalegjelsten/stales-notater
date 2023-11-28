---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-4-3 Bilder og lyd/","title":"IT1-4-3 Bilder og lyd","tags":["it1","forelesning"]}
---


# IT1-4-3 Bilder og lyd
2023-11-16 IT1

Læringsmål:
- Kunne forklare hvordan punktgrafikk er bygget opp
- Kunne forklare hvordan lyd digitaliseres
- Kunne forklare forskjellen mellom tapsfri komprimering og destruktiv komprimering

---
<!-- _class: tittel -->

# 4.3 Bilder

# Les s. 141–142

Gjør oppgave 4.07–4.10 s. 165

---

## Punktgrafikk

- [Youtube: lag bilder i Excel](https://www.youtube.com/watch?v=UBX2QQHlQ_I)
- Punktgrafikk (raster) er den vanligste typen bilder.
- Bildene er rutenett med punkter (piksler) med ulike farger

---

## Lag eget Excelbilde

- Vi lager først et enkelt bilde sammen
- Prøv selv: konvertering fra bilde til regneark 👉 [http://github.andrewt.net/mosaic/](http://github.andrewt.net/mosaic/)

---
<!-- _class: tittel -->

# Egenarbeid bilder

Les resten av kapittel 4.3 (s. 143–148). Legg spesielt merke til forskjellen mellom tapsfri og destruktiv komprimering.

Skriv ned forskjellen på tapsfri og destruktiv komprimering.

---

<!-- _class: tittel -->

# 4.5 Lyd

---

## Analog lydbølge

![h:250px](https://manual.audacityteam.org/m/images/e/ef/waveformabstract.png)

En lydbølge lufta kan spilles inn med mikrofon og analogt opptaksutstyr. Da lagres informasjonen som et signal med:
* $y$-aksen: elektrisk spenning
* $x$-aksen: tid

---

## Digitalisering av lydbølge
![h:250px](https://manual.audacityteam.org/m/images/e/e2/waveform_digital.png)

Vi digitaliserer (tallfester) lyden for å kunne lagre den på digitale enheter.

---

## Samplingsfrekvens
![h:250px](https://manual.audacityteam.org/m/images/0/0e/waveform_sample_rates.png)

- Samplingsfrekvensen er hvor mange målinger vi gjør av signalet per sekund.
- Standard samplingsfrekvens for lyd: 44 100 Hz = 44,1 KHz

* Viktig forskjell:
	* Frekvens: hvor mange bølgetopper på det analoge signalet per sekund
	* Samplingsfrekvens: hvor ofte vi tar målinger per sekund

---

## Nøyaktighet / bit depth
![h:250px](https://manual.audacityteam.org/m/images/8/85/waveform_sample_formats.png)

- Venstre: Lyd med 3 bit kan bare digitaliseres til $2^{3}=8$ ulike lydnivåer
- Høyre: lyd med 5 bit kan digitaliseres til $2^{5}=32$ ulike lydnivåer
- 16 bit er standarden for digital lyd på CD, Spotify, YouTube

---

## Kort oppsummering
![h:250px](https://manual.audacityteam.org/m/images/8/85/waveform_sample_formats.png)

- Lydbølger kan spilles inn som et analogt signal hvor den elektriske spenningen varierer med tiden.
- Lydbølger kan digitaliseres ved å *sample* dem
- Vanlig CD-lyd
	- Samplingfrekvens: 44,1 KHz
	- Nøyaktighet: 16 bit

---

<!-- _class: tittle -->

# Egenarbeid lyd

Skriv ned en forklaring på hvordan vi digitaliserer lydopptak.
