<script>
	import { browser as IsInBrowser } from '$app/environment';
	import { onMount, onDestroy } from 'svelte';

	let isAuthenticated = false;
	let items = [];

	onMount(() => {
		if (IsInBrowser === true) {
			items.push({
				id: window.crypto.randomUUID(),
				title: 'samowar',
				isVirtual: false
			});
			items.push({
				id: window.crypto.randomUUID(),
				title: 'lemke',
				isVirtual: false
			});
			items.push({
				id: window.crypto.randomUUID(),
				title: 'muha',
				isVirtual: false
			});

			items = items;
		}
	});

	onDestroy(() => {});
</script>

<article>
	{#if isAuthenticated === true}
		{#each items as item (item.id)}{/each}
	{:else}
		not isAuthenticated
	{/if}
</article>

<style>
	article {
		display: grid;
		grid-template-columns: 1fr;
		grid-template-rows: 1fr 1fr 1fr;
		gap: var(--main-grid-gap);
		height: 100%;
	}
</style>

