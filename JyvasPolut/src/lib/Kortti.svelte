<script lang="ts">
	interface Props {
		id: number;
		title: string;
		desc: string;
		kuva: string;
	}

	let { id, title, kuva, desc }: Props = $props();
</script>

<div class="card">
	<img class="card-image" src={kuva} alt={title} />
	<div class="card-content">
		<h2>Paikka {id}: {title}</h2>
		<p>{desc}</p>
	</div>
</div>

<style>
	.card {
		border-radius: 16px;
		overflow: hidden;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.15);
		background: white;
		transition: transform 0.2s ease;
	}

	.card:hover {
		transform: translateY(-15px);
	}

	.card-image {
		width: 100%;
		height: 180px;
		object-fit: cover;
	}

	.card-content {
		padding: 8px;
	}
</style>
