<script lang="ts">
	interface Props {
		text: string;
	}
	let { text }: Props = $props();
</script>

<header>
	<h1>{text}</h1>
</header>

<style>
	header {
		position: relative;
		width: 100%;
		height: 12em;
		text-shadow: 2px 2px 2px rgba(230, 230, 230, 0.5);
		box-shadow: 0px 5px 10px rgba(0, 0, 0, 0.5);
		background: linear-gradient(to bottom, #0F172A, #113139, #134E4A);
		padding: 0;
	}
	h1 {
		position: absolute;
		left: 50%;
		top: 50%;
		transform: translate(-50%, -50%);
		font-size: 4em;
		margin: 0;
		color: rgba(232, 228, 228, 0.76);
	}
</style>
