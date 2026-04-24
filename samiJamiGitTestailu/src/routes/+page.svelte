<script lang="ts">
	import Kortti from '$lib/Kortti.svelte';
	import Button from '$lib/Button.svelte';

	function toggle(id: number) {
		napit = napit.map((n) => (n.id === id ? { ...n, paalla: !n.paalla } : n));
	}
	let napit = $state([
		{ id: 1, paalla: false },
		{ id: 2, paalla: false },
		{ id: 3, paalla: false }
	]);
</script>

<Kortti id={1} title="Esimerkkikortti" desc="Kortin kuvaus" kuva="/placeholder.jpg" />

{#each napit as nappi (nappi.id)}
	<Button text={nappi.paalla ? '🔴' : '🟢'} onClick={() => toggle(nappi.id)} disabled={false} />

	{#if nappi.paalla}
		<p>Filtteri {nappi.id} päällä</p>
	{/if}
{/each}
