---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-1-7 Tabeller/","title":"IT1-1-7 Tabeller","tags":["it1","forelesning"]}
---


# IT1-1-7 Tabeller

## Læringsmål

- Å lage tabeller i HTML
- Å bruke `colspan` og `rowspan`
- For de avanserte: bruke klasser til å endre utseendet på celler
 <table border="1">
			<tr>
					<td>Celle 1</td>
					<td>Celle 2</td>
					<td>celle 5</td>
			</tr>
			<tr>
					<td rowspan="2">Celle 3</td>
					<td colspan="2">Celle 4</td>
			</tr>
			<tr>
					<td>hei</td>
					<td>du</td>
			</tr>
	</table>

---

## Lage tabeller

- En tabell omsluttes av HTML-elementet `<table>…</table>`
- `<tr>` gir en ny rad i tabellen
- `<td>` gir en ny celle i tabellen
- `<th>` gir en kolonneoverskrift i tabellen

---

### Eksempel på tabell

Følgende kode gir en tabell med 2 rader (på grunn av de 2 `tr`-elementene) og 2 kolonner (på grunn av de to `td`-elementene i hver `tr`)

```html
<table border="1">
  <tr>
    <td>Celle 1</td>
    <td>Celle 2</td>
  </tr>
  <tr>
    <td>Celle 3</td>
    <td>Celle 4</td>
  </tr>
</table>
```

Det kan være lurt å bruke attributten `border="1"` for å tegne en ramme rundt hver celle i tabellen. Da er det mye enklere å se hva som skjer.

---

## Slå sammen rader og kolonner

- Vi kan slå sammen flere celler med `rowspan` og `colspan`.
- Koden som hører til tabellen nedenfor kan du se på neste side.

<table border="1">
	<tr>
		<td style="border: 2px solid #ddd;">Celle 1</td>
		<td style="border: 2px solid #ddd;">Celle 2</td>
		<td style="border: 2px solid #ddd;">celle 5</td>
	</tr>
	<tr>
		<td rowspan="2" style="border: 2px solid #ddd;">Celle 3</td>
		<td colspan="2" style="border: 2px solid #ddd;">Celle 4</td>
	</tr>
	<tr>
		<td style="border: 2px solid #ddd;">hei</td>
		<td style="border: 2px solid #ddd;">du</td>
	</tr>
</table>
	
---
```html
<table border="1">
	<tr>
		<td>Celle 1</td>
		<td>Celle 2</td>
		<td>celle 5</td>
	</tr>
	<tr>
		<td rowspan="2">Celle 3</td>
		<td colspan="2">Celle 4</td>
	</tr>
	<tr>
		<td>hei</td>
		<td>du</td>
	</tr>
</table>
```

---

## Endre på stilen i tabellen

- Man kan endre på stilen til et HTML-element ved å bruke attributten `style=""`.
	- Med `style="background-color: black;"` så får HTML-elementet svart bakgrunn
	- Med `style="background-color: black; color: white;"` så får HTML-elementet svart bakgrunn og hvit tekst

### Eksempel på bruk av style

```html
<tr>
  <td style="background-color: darkorchid; color: whitesmoke;">
    Dette blir en vakker celle!
  </td>
  <td>Denne cellen blir helt vanlig.</td>
</tr>
```

<table border="4">
<tr>  
	<td style="background-color: darkorchid; color: whitesmoke;">Dette blir en vakker celle!</td>
	<td>Denne cellen blir helt vanlig.</td>
</tr>
</table>

---

## Avansert endring av stilen på HTML-elementer

- Vi kan definere **klasser** i HTML ved å legge til attributten `class="KLASSENAVN"`
- Alle HTML-elementer som har klassen `KLASSENAVN` vil få samme stil
- Vi bestemmer stilen til hver klasse i `<style>…</style>` i `<head>`. Se eksempelet på neste slide. Merk at klassenavnene skrives med et punktum `.` først inne i `style`. 
	- Koden vi legger inn i `style` er CSS-kode. Vi skal lære mer om CSS senere i år.

---

```html
<html>
  <head>
    <style>
      .matte {background-color: lightskyblue;}
      .it {background-color: lightseagreen;}
    </style>
  </head>
  <body>
    <table border="1">
      <tr>
        <td>Vanlig celle</td>
        <td class="matte">Mattecelle</td>
        <td class="it">IT-celle</td>
      </tr>
    </table>
  </body>
</html>
```

---
