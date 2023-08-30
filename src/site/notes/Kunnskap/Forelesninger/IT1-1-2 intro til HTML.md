---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-1-2 intro til HTML/","title":"IT1-1-2 intro til HTML","tags":["it1","forelesning"]}
---


# IT1-1-2 intro til HTML

## Læringsmål
- Forklare strukturen i et HTML dokument
- Bruke tagger til å formatere tekst i HTML
- ~~~Bli kjent med Visual Studio Code~~~
---

## HTML
* HTML er et markeringsspråk
* HTML gir struktur og innhold til nettsidene
* HTML tolkes av nettleseren (Chrome, Firefox, Edge, Safari)
* `Jeg liker <b>fete</b> bokstaver` → Jeg liker **fete** bokstaver
* HTML består av elementer med *tagger* som `<b> <p> <br> <a> <img>`

![bg left:30% contain](/img/user/Excalidraw/html-element.excalidraw.png)

---

## Din første(?) nettside
- Lagre koden nedenfor som en fil med filendelse `.html`. 
- Åpne filen i nettleseren din (velg Fil → Åpne eller <kbd>ctrl</kbd>+<kbd>o</kbd>)

```html
<html>
<body>
<h1>Min nettside</h1>
Dette er min første nettside.
<p>Dette er et avsnitt</p>
</body>
</html>
```

*Hvorfor tror dere vi foretrekker at teksten skrives mellom `<p>`-taggene?*

---

## Oppbygning av HTML-dokument
```html
<html lang="no">
	<head>
		<meta charset="UTF-8">
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>Nettside</title>
		<script>console.log("Denne teksten kommer i konsollen")</script>
		<link rel="stylesheet" href="stilark.css">
	</head>
	<body>
	<p>Her kommer innholdet</p>
	</body>
</html>
```

---

## Nyttige HTML tagger
- `<p>…</p>` gir avsnitt
- `<br>` gir linjeskift
- `<h1>…</h1>` gir den største overskriften
- `<b>…</b>` gir fet tekst
- `<i>…</i>` gir kursiv tekst

---

## Nyttige HTML tagger forts…
- `<ul>…</ul>` gir en liste uten nummerering
- `<ol>…</ol>` gir en liste med nummerering
- `<li>…</li>` markerer hvert element i lista
- `<mark>…</mark>` markerer tekst
- `<a href="URL.html">…</a>` lager lenker
- `<img src="URL-TIL-BILDE.jpg">` gir bilde
- OBS: `href=` og `src=` er såkalte *attributter* som hører til HTML-elementet.
 
 ---

## VSCode
![bg left](https://user-images.githubusercontent.com/35271042/118224532-3842c400-b438-11eb-923d-a5f66fa6785a.png)

- Visual Studio Code er en tekstbehandler fra Microsoft
- Gjør det mye enklere å skrive kode!
- Last ned til neste time! (**Lekse**)
