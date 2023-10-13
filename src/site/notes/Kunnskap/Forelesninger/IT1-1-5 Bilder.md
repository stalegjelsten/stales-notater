---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-1-5 Bilder/","title":"IT1-1-5 bilder","tags":["forelesning","it1"]}
---


# IT1-1-5 bilder

## Læringsmål

- Sette inn bilder på nettsider
- Forklare forskjellen på vektorgrafikk og rastergrafikk
- Gjøre enkle endringer på vektorgrafikk

---

## Bilder

- Bilder settes inn med `<img src="filnavn.jpg">`
- `<img>` har disse nyttige attributtene:
	- `src` (source) er URL (nettadressen) til bildefila
	- `alt` er alternativ tekst for bildet. *Bør alltid være med*. `alt` gjør det mulig for svaksynte å forstå hva bildet symboliserer.
	- `height` er høyden på bildet i piksler
	- `width` er bredden på bildet i piksler

### Oppgave

Legg inn `alt`-tekst på Rumpeldunkbildet ditt.

---

## Rastergrafikk

![bg right:50% contain](https://upload.wikimedia.org/wikipedia/commons/3/3b/Rgb-raster-image.svg)

- Består av bildepunkter (piksler) med fargeverdier
- Zooming gjør bildene uskarpe
- Filtyper: `JPEG`, `JPG`, `PNG`
- Bildene kan redigeres med programmer som
	- Paint (allerede installert på Windows)
	- paint.net
	- GIMP (avansert gratisprogram)

---

## Vektorgrafikk

- Vektorgrafikk: instruksjoner for hvordan datamaskinen skal tegne linjer, sirkler osv.
- Uendelig zoom og tar lite lagringsplass
- Uegnet til å lagre fotografier
- Filtyper: `SVG`, `EPS`, `PDF` (PDF kan inneholde både vektor- og rastergrafikk)

![bg right:50% contain](https://nhscreative.org/wp-content/uploads/2010/10/Raster-vs-Vector-2.jpg)

---

### Oppgave – lag din egen vektorgrafikk

```html
<svg name="hovedramme-usynlig" width="500" height="500">
  <rect x="0" y="0" width="440" height="100" style="fill: darkred;" />
  <rect x="0" y="100" width="440" height="150" style="fill: darkblue;" />
  <rect x="0" y="250" width="440" height="100" style="fill: darkred;" />
  <circle cx="180" cy="150" r="60" stroke="none" fill="white" />
</svg>
```

- Legg inn koden over i `body` i HTML
- Det blir nesten likt som flagget under. Klarer du å fikse feilene?
- Ta gjerne utgangspunkt i koden over, og lag Bangladesh sitt flagg.

![h:80](https://upload.wikimedia.org/wikipedia/commons/5/56/Flag_of_Laos.svg)
