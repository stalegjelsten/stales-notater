---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-2-2 Bilder i CSS/","title":"IT1-2-2 Bilder i CSS","tags":["it1","forelesning"]}
---


# IT1-2-2 Bilder i CSS

## Læringsmål

- Endre kantlinjer på bilder
- Endre utsnitt av bilder
- La et bakgrunnsbilde fylle hele nettsiden

---

## Kantlinjer og avrundede bilder

```css
img {
  width: 400px;
  border: 15px solid burlywood;
}
```

<img style="border:15px solid burlywood; width:400px;" href="https://stalegjelsten.github.io/IT1/36-css-bilder/veps.jpg">

---

## Kantlinjer og avrundede bilder

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Bilder og CSS</title>
    <style>
      .border {
        width: 400px;
        border: 15px solid burlywood;
      }
      .arvrundet {
        width: 400px;
        border: 15px solid green;
        border-radius: 20%;
      }
      .bildeiboks {
        width: 400px;
        height: 400px;
        object-fit: ;
        object-position: left;
        border: 15px solid red;
      }
    </style>
  </head>
  <body>
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="border"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="arvrundet"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="bildeiboks"
    />
  </body>
</html>
```

## Kantlinjer og avrundede bilder

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Bilder og CSS</title>
    <style>
      .border {
        width: 400px;
        border: 15px solid burlywood;
      }
      .arvrundet {
        width: 400px;
        border: 15px solid green;
        border-radius: 20%;
      }
      .bildeiboks {
        width: 400px;
        height: 400px;
        object-fit: ;
        object-position: left;
        border: 15px solid red;
      }
    </style>
  </head>
  <body>
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="border"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="arvrundet"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="bildeiboks"
    />
  </body>
</html>
```

## Kantlinjer og avrundede bilder

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Bilder og CSS</title>
    <style>
      .border {
        width: 400px;
        border: 15px solid burlywood;
      }
      .arvrundet {
        width: 400px;
        border: 15px solid green;
        border-radius: 20%;
      }
      .bildeiboks {
        width: 400px;
        height: 400px;
        object-fit: ;
        object-position: left;
        border: 15px solid red;
      }
    </style>
  </head>
  <body>
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="border"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="arvrundet"
    />
    <img
      src="veps.jpg"
      alt="Nærbilde av flere veps som spiser syltetøy"
      class="bildeiboks"
    />
  </body>
</html>
```

---

## Bakgrunnsbilde som fyller nettsiden

```html
<style>
  html {
    background-image: url("BILDE.jpg");
    background-size: cover;
    background-repeat: no-repeat;
    height: 100vh;
    overflow: hidden;
  }
</style>
```
