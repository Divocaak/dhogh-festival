<script>
	export let label;
	export let artists;
	export let color = 'var(--shadow)';
</script>

<div class="wrapper" style="--color: {color};">
	<h2>{label}</h2>
	<p class="pp-supply">
		{#each artists as artist}{artist}&emsp;{/each}
	</p>
</div>

<style>
	:root {
		--color: var(--shadow);
	}

	.wrapper {
		margin-bottom: 8rem;
	}

	.wrapper h2 {
		color: var(--color);
		border-bottom: 2px solid var(--color);
		font-weight: 250;
		padding-bottom: 1.5rem;
		margin: 0;
	}

	.wrapper p {
		color: var(--color);
		text-transform: uppercase;
		font-size: 2rem;
	}

	@media (max-width: 1200px) {
		.wrapper p{
			position: relative;
			font-size: var(--fs-24);
		}
	}

</style>
