---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-2-2 Bilder i CSS/","title":"IT1-2-2 Bilder i CSS","tags":["it1","forelesning"]}
---


# IT1-2-2 Bilder i CSS

## Læringsmål

- Endre kantlinjer på bilder
- Endre utsnitt av bilder
- La et bakgrunnsbilde fylle hele nettsiden

---

## Kantlinjer

```css
img {
  width: 200px;
  border: 15px solid burlywood;
}
```

<img style="border:15px solid burlywood; width:200px;" src="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## Kantlinjer og avrundede bilder

```css
img {
  width: 200px;
  border: 15px solid burlywood;
  border-radius: 20%;
}
```

<img style="border:15px solid burlywood; width:200px; border-radius:20%;" src="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## Tilpasse bilde til rammen

```css
img {
  width: 200px;
  height: 200px;
  object-fit: contain;
  border: 15px solid red;
}
```

<img style=" width: 200px;
				height: 200px;
				object-fit: contain;
				border: 15px solid red;
" src="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## La bilder fylle HTML-elementet

```css
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
  border: 15px solid red;
}
```

<img style=" width: 200px;
				height: 200px;
				object-fit: cover;
				object-position: right;
				border: 15px solid red;
" src="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## Justere posisjon til bilder

```css
img {
  width: 200px;
  height: 200px;
  object-fit: cover;
  object-position: right;
  border: 15px solid red;
}
```

<img style="width: 200px;
				height: 200px;
				object-fit: cover;
				border: 15px solid red;
" src="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## Bakgrunnsbilde som fyller nettsiden

```css
html {
  background-image: url("BILDE.jpg");
  background-size: cover;
  background-repeat: no-repeat;
  height: 100vh;
  overflow: hidden;
}
```

`100vh` betyr 100 % av _viewport height_ – vi setter altså høyden av html-elementet til hele høyden av det synlige vinduet i nettleseren.
