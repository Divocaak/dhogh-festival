<script>
	export let value;

	function breakIntoTwoLines(text) {
		const words = text.trim().split(' ');
		const middle = Math.floor(words.length / 2);
		return `${words.slice(0, middle).join(' ')}<br>${words.slice(middle).join(' ')}`;
	}
</script>

<div class="wrapper">
	<h2>{@html breakIntoTwoLines(value.label)}</h2>
	<p>{value.desc}</p>
</div>

<style>
	.wrapper {
		display: flex;
		flex-direction: column;
		width: 380px;
		text-align: center;
	}

	.wrapper p {
		font-size: var(--fs-20);
		margin: 0;
	}

	.wrapper h2 {
		margin: 0;
		font-size: var(--fs-48);
		font-weight: 300;
		padding-bottom: 1.5rem;
	}

	@media (max-width: 1200px) {
		.wrapper {
			width: 100%;
		}
	}
</style>
