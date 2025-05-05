<script>
	export let label = 'clck';
	export let onclick;
	export let bgColor = 'var(--black)';
	export let txtColor = 'var(--shadow)';
	export let marginAuto = true;
</script>

<button
	on:click={() => onclick()}
	style="--background-color: {bgColor}; --text-color: {txtColor};"
	class:margin-auto={marginAuto}>{label}</button
>

<style>
	:root {
		--text-color: var(--shadow);
		--background-color: var(--black);
	}

	button {
		position: relative;
		display: block;
		width: max-content;

		border: none;
		cursor: pointer;

		text-transform: uppercase;
		background-color: var(--background-color);
		color: var(--text-color);
		padding: 1.25rem 1.75rem;

		transition: all 0.2s ease-in-out;
	}

	button:hover {
		color: var(--background-color);
		background-color: var(--text-color);
	}

	.margin-auto {
		margin: auto;
	}
</style>
