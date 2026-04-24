<script lang="ts">
	interface Props {
		text: string;
	}
	let { text }: Props = $props();
</script>

<footer>
	<p>{text} / {new Date().getFullYear()}</p>
</footer>

<style>
	footer {
		position: bottom;
		bottom: 0;
		left: 0;
		width: 100%;
		/* background-color: rgb(171, 187, 169); */

		color: rgba(0, 0, 0, 0.76);
		height: 2.5em;
		box-shadow: 0 5px 10px rgba(0, 0, 0, 0.5);
		display: flex;
		justify-content: center;
		align-items: center;
		text-shadow: 2px 2px 1px rgba(200, 200, 200, 0.38);
	}
</style>
