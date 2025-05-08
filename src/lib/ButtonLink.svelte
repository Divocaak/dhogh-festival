<script>
	export let label = 'clck';
	export let href = '';
	export let target = '_blank';
	export let bgColor = 'var(--black)';
	export let txtColor = 'var(--shadow)';
	export let marginAuto = true;
	export let smallerPaddings = false;
	export let disabled = false;
	export let isFooter = false;
</script>

<a
	style="--background-color: {bgColor}; --text-color: {txtColor};"
	class:margin-auto={marginAuto}
	class:smaller-paddings={smallerPaddings}
	class:disabled
	class:is-footer={isFooter}
	{href}
	{target}>{label}</a
>

<style>
	:root {
		--text-color: var(--shadow);
		--background-color: var(--black);
	}

	a {
		position: relative;
		display: block;
		width: max-content;

		text-transform: uppercase;
		background-color: var(--background-color);
		color: var(--text-color);
		padding: 1.25rem 1.75rem;

		transition: all 0.2s ease-in-out;
	}

	a:hover {
		color: var(--background-color);
		background-color: var(--text-color);
	}

	.margin-auto {
		margin: auto;
	}

	.smaller-paddings {
		padding: 0.75rem 1.25rem;
	}

	.disabled {
		pointer-events: none;
		cursor: default;
		color: var(--disabled);
		text-decoration: line-through;
	}

	.disabled:hover {
		color: var(--background-color);
		background-color: var(--disabled);
	}

	.is-footer{
		font-size: var(--fs-28);
	}
</style>
