<script lang="ts">
	import Modal from '$lib/Modal.svelte';

	interface Props {
		nimi: string;
		desc: string;
		title: string;
		kuva: string[] | null;
		hideProduct: () => void;
	}

	let { nimi, desc, kuva, hideProduct }: Props = $props();
	let kuvaIndex = $state(0);
	let nykyinenKuva: string | null = $derived(kuva ? kuva[kuvaIndex] : null);

	function selaaKuviaEteen() {
		if (kuva && kuva.length > 0) {
			if (kuvaIndex < kuva?.length - 1) {
				kuvaIndex++;
			} else {
				kuvaIndex = 0;
			}
		}
	}
	function selaaKuviaTaakse() {
		if (kuva && kuva.length > 0) {
			if (kuvaIndex > 0) {
				kuvaIndex--;
			} else {
				kuvaIndex = kuva.length - 1;
			}
		}
	}
</script>

<Modal>
	{#snippet header()}
		<h1>{nimi}</h1>
	{/snippet}

	<p>{desc}</p>
	<div class="moreinfo">
		<div class="details">{desc}</div>
		<div class="image">
			{#if nykyinenKuva}
				<button onclick={selaaKuviaTaakse}>&lt</button>
				<img src={nykyinenKuva} alt={desc} height="200px" width="300px" />
				<button onclick={selaaKuviaEteen}>&gt;</button>
			{:else}
				<div class="placeholderimg">👁️‍🗨️</div>
			{/if}
		</div>
	</div>

	{#snippet footer()}
		<button onclick={hideProduct}>Sulje</button>
	{/snippet}
</Modal>

<style>
	.moreinfo {
		display: flex;
		flex-direction: row;
	}

	.details {
		width: 50%;
		font-style: italic;
		margin-left: 2em;
		padding: 1em;
	}

	.image {
		width: 50%;
		display: flex;
		justify-content: center;
	}

	img {
		max-width: 50%;
		max-height: auto;
		border-radius: 30px;
	}

	.placeholderimg {
		font-size: 8em;
	}
</style>
