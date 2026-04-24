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

<Header text={appi.name} />
<main class="content">
	{@render children()}
</main>
<Footer text={appi.cr} />

<style>
	.content {
		padding-bottom: 2.5em; /* footerin korkeus */
	}
	:global(html, body) {
		margin: 0;
		padding: 0;
	}

	:global(*) {
		box-sizing: border-box;
	}
</style>
