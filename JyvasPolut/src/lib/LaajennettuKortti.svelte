<script lang="ts">
	import Modal from '$lib/Modal.svelte';

	interface Props {
		nimi: string;
		desc: string;
		title: string;
		kuva: string | null;
		hideProduct: () => void;
	}

	let { nimi, desc, kuva, hideProduct }: Props = $props();
</script>

<Modal>
	{#snippet header()}
		<h1>{nimi}</h1>
	{/snippet}

	<!-- muut tiedot default-osaan, tähän ei tarvitse tehdä muutoksia -->
	<p>{desc}</p>
	<div class="moreinfo">
		<div class="details">{desc}</div>
		<div class="image">
			{#if kuva}
				<img src={kuva} alt={desc} />
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
