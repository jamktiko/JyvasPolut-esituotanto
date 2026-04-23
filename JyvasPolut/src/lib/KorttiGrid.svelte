<script lang="ts">
	import { tiedot } from '$lib/korttiInfo';
	import Kortti from '$lib/Kortti.svelte';
	import LaajennettuKortti from '$lib/LaajennettuKortti.svelte';

	let selected = $state<(typeof tiedot)[number] | null>(null);

	type KorttiItem = (typeof tiedot)[number];
	function open(item: KorttiItem) {
		selected = item;
	}

	function close() {
		selected = null;
	}
</script>

<div class="grid">
	{#each tiedot as item (item.id)}
		<button onclick={() => open(item)}>
			<Kortti {...item} />
		</button>
	{/each}
</div>

{#if selected}
	<LaajennettuKortti
		nimi={selected.title}
		desc={selected.desc}
		title={selected.title}
		kuva={selected.kuva}
		hideProduct={close}
	/>
{/if}

<style>
	.grid {
		display: grid;
		grid-template-columns: repeat(3, 300px);
		gap: 50px;
		justify-content: center;
		padding: 50px;
	}
	button {
		all: unset;
		display: block;
		cursor: pointer;
	}
</style>
