---
{"dg-publish":true,"permalink":"/Kunnskap/each blokker i Svelte/","title":"each blokker i Svelte","tags":["it1","svelte"]}
---


# each blokker i Svelte
Each blokker gjør det enkelt å lage for-løkker.

{% raw %}
```html
<script>
	let cats = [
		{ id: 'J---aiyznGQ', name: 'Keyboard Cat' },
		{ id: 'z_AbfPXTKms', name: 'Maru' },
		{ id: 'OUtn3pvWmpg', name: 'Henri The Existential Cat' }
	];
</script>

<h1>The Famous Cats of YouTube</h1>

<ul>
	<!-- open each block. i is the index (so #each cats as cat would also work) -->
	{#each cats as cat, i}
		<li><a target="_blank" href="https://www.youtube.com/watch?v={cat.id}" rel="noreferrer">
			{i + 1}: {cat.name}
		</a></li>
	{/each}
	<!-- close each block -->
</ul>
```

{% endraw %}
