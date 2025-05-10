<script>
	export let name = 'name';
</script>

<div>
	<h1>{name}</h1>
</div>

<style>
	div {
		background-color: var(--black);
		border-radius: var(--card-border-radius);
        display: flex;
        flex-direction: column;
        padding: 1rem 0;

        max-width: 250px;
	}

	h1 {
        margin: auto;
		color: var(--shadow);
        width: 100%;
        text-align: center;
        font-size: var(--fs-32);
	}

	@media (max-width: 1200px) {}
	div{
		width:100%;
		max-width: calc(100% - 3rem);
	}
</style>
