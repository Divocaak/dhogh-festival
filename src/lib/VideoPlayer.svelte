<script>
	export let src;
</script>

<video {src} autoplay muted loop playsinline preload="auto"></video>

<style>
	video {
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
	}
</style>
