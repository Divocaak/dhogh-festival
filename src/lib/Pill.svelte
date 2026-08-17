<script>
	export let label;
	export let inverted = false;
</script>

<span class="pill" class:inverted>{label}</span>

<style>
	.pill {
		display: inline-flex;
		align-items: center;
		gap: 6px;

		padding: 7px 13px;
		border-radius: 999px;
		border: 1px solid var(--black);
		background-color: var(--black);
		color: var(--yellow);

		font-size: 13px;
		font-weight: 600;
		line-height: 1;
		white-space: nowrap;

		text-transform: uppercase;
	}

	.inverted {
		border: 1px solid var(--yellow);
		background-color: var(--yellow);
		color: var(--black);
	}
</style>
