<script>
	import ButtonLink from './ButtonLink.svelte';
</script>

<div class="footer">
	<ButtonLink
		label="facebook"
		href="https://www.facebook.com/DHOGHTEAM"
		marginAuto={false}
		isFooter={true}
	/>
	<ButtonLink
		label="instagram"
		href="https://www.instagram.com/dhoghteam/"
		marginAuto={false}
		isFooter={true}
	/>
	<ButtonLink
		label="dhoghteam@gmail.com"
		href="mailto:dhoghteam@gmail.com"
		marginAuto={false}
		isFooter={true}
	/>
</div>

<style>
	.footer {
		display: flex;
		flex-direction: row;
		position: relative;
		width: 100%;
		justify-content: space-evenly;
		margin: auto;
		bottom: 0;
		height: 100%;
		margin-top: 7rem;
	}

	@media (max-width: 1200px) {
		.footer {
			flex-direction: column;
		}
	}
</style>
