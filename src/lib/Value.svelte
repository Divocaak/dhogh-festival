<script>
	export let img;
	export let label;
	export let text;
</script>

<div class="wrapper">
	<div class="image" style={`background-image: url("${img}")`}></div>
	<h2>
		{#each label.split(' ') as word}
			<span>{word}</span>
		{/each}
	</h2>
	<p>{text}</p>
</div>

<style>
	.wrapper {
		display: flex;
		flex-direction: column;
		width: 380px;
		text-align: center;

		gap: 2rem;
	}

	.image {
		width: 100%;
		aspect-ratio: 360 / 306;
		background-position: center;
		background-repeat: no-repeat;
		background-size: cover;

		border-radius: 4%;
	}

	.wrapper h2 {
		margin: 0;
		font-size: var(--fs-48);
		font-weight: 300;
		word-wrap: break-word;
	}

	.wrapper h2 span {
		display: block;
	}

	.wrapper p {
		font-size: var(--fs-20);
		margin: 0;
	}

	@media (max-width: 1200px) {
		.wrapper {
			width: 100%;
		}
	}
</style>
