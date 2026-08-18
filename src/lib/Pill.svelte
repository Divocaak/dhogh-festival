<script>
	export let label;
	export let tix = false;
	export let hoverfx = false;
</script>

<span class="pill tt-uppercase {tix ? 'tix-button' : 'f4'}" class:tix-pill={tix} class:hoverfx>
	{label}
</span>

<style>
	.pill {
		display: inline-flex;
		align-items: center;
		gap: 6px;

		padding: 7px 13px;
		border-radius: 999px;
		border: 1px solid var(--black);
		background-color: var(--yellow);
		color: var(--black);

		transition: all 0.17s ease-in-out;
	}

	.tix-pill {
		padding: 10px 50px;
		background-color: var(--black);
		color: var(--yellow);
	}

	.hoverfx:hover {
		border-color: var(--white) !important;
		background-color: var(--white) !important;
		color: var(--black) !important;
	}
</style>
