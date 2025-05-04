<script>
	export let imagePath;
</script>

<div style="background-image: url('{imagePath}');">
	<slot></slot>
</div>

<style>
	div {
position: relative;
		height: 100vh;
		width: 100vw;
		padding: 0;
		margin: 0;

        background-attachment: fixed;
		background-position: center;
		background-size: cover;
		background-repeat: no-repeat;
	}
</style>
