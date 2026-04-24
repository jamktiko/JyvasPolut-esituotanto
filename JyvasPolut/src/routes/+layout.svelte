<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';
	import { appi } from '$lib/appInfo';
	import Header from '$lib/Header.svelte';
	import Footer from '$lib/Footer.svelte';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="min-h-screen bg-gradient-to-r from-[#0F172A] to-[#022C22]">
	<Header text={appi.name} />

	<main class="content">
		{@render children()}
	</main>

	<Footer text={appi.cr} />
</div>

<style>
	.content {
		padding-bottom: 2.5em;
	}

	:global(html, body) {
		margin: 0;
		padding: 0;
	}

	:global(*) {
		box-sizing: border-box;
	}
</style>