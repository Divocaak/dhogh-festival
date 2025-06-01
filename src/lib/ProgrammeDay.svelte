<script>
	export let programme;
	export let color = 'var(--shadow)';
</script>

<div class="wrapper" style="--color: {color};">
	<h2>{programme.label}</h2>
	<p class="pp-supply">
		{#each programme.artists as artist}{@html artist}&emsp;{/each}
	</p>
	<p class="pp-supply">
		{#each programme.other as other}{@html other}&emsp;{/each}
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
		font-size: var(--fs-32);
	}

	.wrapper p:last-of-type {
		font-size: var(--fs-24);
		font-weight: 200;
	}

	@media (max-width: 1200px) {
		.wrapper p {
			font-size: var(--fs-24);
		}

		.wrapper p:last-of-type {
			font-size: var(--fs-20);
			white-space: normal;
  word-break: normal;
		}
	}
</style>
