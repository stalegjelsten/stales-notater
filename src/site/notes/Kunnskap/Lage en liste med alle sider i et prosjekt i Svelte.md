---
{"dg-publish":true,"permalink":"/Kunnskap/Lage en liste med alle sider i et prosjekt i Svelte/","title":"Lage en liste med alle sider i et prosjekt i Svelte","tags":["it1","svelte"]}
---


# Lage en liste med alle sider i et prosjekt i Svelte

>[!warning] Advarsel
>
> Følgende oppskrift er kun testet av meg lokalt. Den brukes derfor på eget ansvar.

For å hente ut lenker til alle sidene i et [[Kunnskap/Svelte\|Svelte]]-prosjekt så kan du legge inn følgende kode `src/routes/+page.svelte`. Denne vil forsøke å 
- Hente alle undersider med å søke etter `'./**'`
- Alle undersidene ligger i et objekt hvor nøklene er stien til en side. Vi henter derfor ut alle nøklene fra objektet
	- Vi filtrerer og tar kun med sidene som inkluderer `+page.svelte` i filnavnet
	- Tar bort den innledende `./` og avsluttende `/+page.svelte` i stien
- Skriver ut hver side i en uordnet liste som en lenke

```html
<script>
	const pagesObject = import.meta.glob('./**');
	const pages = Object.keys(pagesObject)
		.filter((key) => key.includes('+page.svelte'))
		.map((item) => item.replace('./', '')
		.replace('/+page.svelte', ''));
</script>

<ul>
	{#each pages as page}
		<li><a href={page}>{page}</a></li>
	{/each}
</ul>
```
