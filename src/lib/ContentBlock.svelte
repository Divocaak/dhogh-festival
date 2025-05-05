<script>
	export let backgroundColor = 'var(--black)';
</script>

<div style="--bg-color: {backgroundColor};">
	<slot></slot>
</div>

<style>
	:root {
		--bg-color: var(--black);
	}

	div {
		position: relative;
		z-index: 10;
		width: 100vw;
		padding: 0;
		margin: 0;
		background-color: var(--bg-color);
	}
</style>
