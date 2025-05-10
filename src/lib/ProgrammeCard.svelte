<script>
	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
	import ButtonLink from './ButtonLink.svelte';
	import FlippingCard from './FlippingCard.svelte';

	export let cardName = 'card name';
	export let imgPath = 'raver.jpg';
	export let desc = 'lorem ipsum';
</script>

<div class="wrapper">
	<FlippingCard widthPx="250px" minHeightPx="300px" minHeightPxSm="400px">
		<div slot="inner" class="inner">
			<div class="bg-image" style="background-image: url('/imgs/artists/{imgPath}');"></div>
			<div class="texts-wrapper">
				<h1>{cardName}</h1>
			</div>
		</div>
		<div slot="backface" class="backface">
			<div class="programme-detail">
				<p class="pp-supply desc">{desc}</p>
			</div>
		</div>
	</FlippingCard>
</div>

<style>
	:root {
		--lead-text-color: var(--shadow);
		--card-background: var(--black);
	}

	.wrapper{
		display: flex;
		padding: 0;
		margin: 0;
	}

	.inner,
	.backface {
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
	}

	.bg-image {
		border-radius: calc(var(--card-border-radius) / 2);
		aspect-ratio: 1/1;
		background-position: center;
		background-repeat: none;
		background-size: cover;
	}

	.texts-wrapper {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: end;
		text-align: end;
		margin: 1rem 0;
		padding: 0 0.5rem;
	}

	.texts-wrapper h1 {
		margin: 0;
		width: 100%;
		text-align: center;
		color: var(--lead-text-color);
		font-size: var(--fs-32);
	}

	.programme-detail {
		display: flex;
		flex-direction: column;
		justify-content: center;
		text-transform: uppercase;
		height: 100%;
		margin: 0 1rem;
	}

	.programme-detail p {
		color: var(--shadow);
		font-size: var(--fs-16);
		line-height: 1.4rem;
	}

	@media (max-width: 1200px) {
		.wrapper {
			width: calc(100% - 3rem);
			padding: 0 1.5rem;
		}
	}
</style>
