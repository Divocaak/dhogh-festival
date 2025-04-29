<script>
	export let padded = false;
    export let backgroundColor = "var(--black)";
</script>

<div class:padded style="--bg-color: {backgroundColor}">
	<slot></slot>
</div>

<style>
:root{
    --bg-color: var(--black);
}

	div {
		position: relative;
		height: 100vh;
		width: 100vw;
		padding: 0;
		margin: 0;
        background-color: var(--bg-color);
	}

	.padded {
		padding-left: 5rem;
        width: calc(100vw - 5rem);
	}
</style>
