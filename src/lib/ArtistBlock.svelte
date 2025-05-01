<script>
	export let imgPath = 'tst.jpg';
	export let name = 'artist';
</script>

<div class="container">
	<img src="{imgPath}" alt="" />
	<h1>{name}</h1>
</div>

<style>
	.container {
		position: relative;
	}

	.container img {
		max-width: 100%;
		height: auto;
		position: relative;
	}

	.container h1 {
		position: relative;
		bottom: 0;
		background-color: var(--shadow);
		margin: 0;
		padding-top: 2rem;
		text-align: center;
	}
</style>
