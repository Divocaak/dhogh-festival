<script>
	export let imgPath = 'tst.jpg';
	export let name = 'artist';
</script>

<div class="container">
	<div class="image" style="background-image: url('/imgs/artists/{imgPath}');"></div>
	<h1>{name}</h1>
</div>

<style>
	.container {
		display: flex;
		flex-direction: column;
	}

	.container .image {
		aspect-ratio: 1 / 1;
		background-size: cover;
		background-position: center;
		background-repeat: no-repeat;
	}

	.container h1 {
		display: flex;
		align-items: flex-end; 
		justify-content: center;

		height: 100%;
		
		padding-top: 2rem;
		margin: 0;

		text-align: center;
		background-color: var(--shadow);
	}
</style>
