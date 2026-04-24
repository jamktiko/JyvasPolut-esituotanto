<script lang="ts">
	let { text, onClick, disabled } = $props();
</script>

<button onclick={onClick} {disabled}>{text}</button>
