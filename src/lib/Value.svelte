<script>
	export let img;
	export let label;
	export let text;
</script>

<div class="wrapper">
	<div class="image" style={`background-image: url("${img}")`}></div>
	<h3 class="f1 tt-uppercase">
		{#each label.split(' ') as word}
			<span>{word}</span>
		{/each}
	</h3>
	<p class="f3">{text}</p>
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

	.wrapper h3 {
		margin: 0;
		word-wrap: break-word;
	}

	.wrapper h3 span {
		display: block;
	}

	.wrapper p {
		margin: 0;
	}

	@media (max-width: 1200px) {
		.wrapper {
			width: 100%;
		}
	}
</style>
