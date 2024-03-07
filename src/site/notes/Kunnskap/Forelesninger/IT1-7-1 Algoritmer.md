---
{"dg-publish":true,"permalink":"/Kunnskap/Forelesninger/IT1-7-1 Algoritmer/","title":"IT1-7-1 Algoritmer","tags":["it1","forelesning"]}
---


# IT1-7-1 Algoritmer
IT1 04.03.2024

> En algoritme er stegvise instruksjoner

---
<!-- _backgroundColor: #f1ccc1 -->
## Den algoritmiske tenkeren

![bg contain](/img/user/Kunnskap/Forelesninger/imgs/algoritmisk-tekning.png)

---

## Opphavet til algoritmer

Al-Khwarizmi fra nåtidens Uzbekistan ga ut to bøker som har vært svært viktige for matematikken i Europa:

1. *Al-Jabr*, 820 evt., la grunnlaget for algebra
2. *Liber Algorismi de numero Indorum* (latinsk oversettelse), 825 evt., forklarte hvordan indere løste tallregning (aritmetikk). Legg merke til at boka heter Liber (bok) Algorismi (av Al-Khwarizmi)

---

## Peanut butter jelly algoritme

<iframe src="https://www.youtube.com/embed/FN2RM-CHkuI" class="youtube" title="" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

---

## En mer presis definisjon av algoritmer

Krav til algoritme:

1. Prosess hvor man tar inn data (inndata/input) og gir tilbake et resultat (utdata/output)
2. Prosessen må beskrevet stegvis i entydige instruksjoner.
3. Hvert steg må lede til neste steg
4. Med samme inndata skal alltid algoritmen gi samme utdata
5. Algoritmen skal helst stoppe en gang

---

## Pseudokode

- *Pseudokode* er programkode som gir et overblikk over hvordan en algoritme eller et program fungerer. 
- Pseudokode skal *ikke* skrives med syntaksen til et programmeringsspråk
- Pseudokode ligner ofte på pythonkode, siden python er et språk med synaks som ligner på vanlig engelsk
- Å *implementere pseudokode* er å oversette pseudokoden til programkoden i riktig programmeringsspråk

![](/img/user/Kunnskap/Forelesninger/imgs/ide-til-programkode.png)

---

## Eksempel pseudokode 7.04

```
Variabel T = hent tall fra brukeren

T = slå sammen T og teksten "0"

T = T / 5

Vis T på skjermen
```

---

## Implementering av pseudokode 7.04

```html
<script>
	let T = "";
	$: resultat = (T + "0") / 5;
</script>

<input type="number" bind:value={T} />
{#if T != "" && T !== null}
	<p>{T} × 5 = {resultat}</p>
{/if}
```

---

```html
<!-- 7.03 -->
<script>
	let x = "";
	let tallvenner = [];
	const finnTallvenner = () => {
		tallvenner = [];
		for (let i = 0; i <= x / 2; i++) {
			const tallpar = [i, x - i];
			tallvenner.push(tallpar);
		}
		return tallvenner;
	};
</script>

<h1>Finn tallvenner</h1>
<input type="number" name="" id="" bind:value={x} />
<button on:click={finnTallvenner}>Finn tallvenner</button>
{#if (tallvenner.length > 0)}
	<p>Tallvennene til {x} er</p>
	<ul>
		{#each tallvenner as tallpar}
			<li>{tallpar.join(" og ")}</li>
		{/each}
	</ul>
{/if}
<!-- SKRIVER EN VELDIG LANG LINJE FOR AT ALL TEKSTEN SKAL FÅ PLASS PÅ SAMME SIDE. JABADABADADOOOOOOOOOOOOOOO -->
```

---

<iframe src="https://www.youtube.com/embed/rL8X2mlNHPM" class="youtube" title="Crash course om algoritmer" loading="lazy" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
