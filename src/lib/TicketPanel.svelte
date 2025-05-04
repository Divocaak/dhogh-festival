<script>
	import ButtonLink from './ButtonLink.svelte';

	export let label;
	export let desc;
	export let texts = [];
	export let imgPath;
	export let price;
	export let priceSecondWave = null;
	export let link;
	export let linkSecondWave = null;
	export let twoCols = false;
</script>

<div class="wrapper" class:two-cols={twoCols}>
	<div class="img"></div>
	<div class="texts">
		<div class="texts-wrapper">
			<h1>{label}</h1>
			<h2>({desc})</h2>
		</div>
		<div class="texts-wrapper">
			{#each texts as text}
				<p>{text}</p>
			{/each}
		</div>
		<div class="texts-wrapper">
			<div class="cta-wrapper">
				<p>{price},-</p>
				<ButtonLink label="koupit" href={link} marginAuto={false} />
			</div>
			{#if priceSecondWave}
				<div class="cta-wrapper">
					<p>{priceSecondWave},-</p>
					<ButtonLink label="koupit" href={linkSecondWave} marginAuto={false} />
				</div>
			{/if}
		</div>
	</div>
</div>

<style>
	h1,
	h2,
	p {
		color: var(--shadow);
		margin: 0.25rem 0;
	}

	.two-cols {
		grid-column-start: 1;
		grid-column-end: 3;
	}

	.wrapper {
		display: flex;
		flex-direction: row;
	}

	.img {
		flex: 1;
		/* min-height: 400px; */
		/* aspect-ratio: 1 / 1; */
		background-image: url('tst.jpg');
		background-size:cover;
		background-position: center;
	}

	.texts {
		flex: 1.5;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		padding-left: 1rem;
	}

	.texts .texts-wrapper {
		margin: 0;
		padding: 0;
	}

	.texts .texts-wrapper:nth-of-type(2) {
		height: 100%;
	}

	.cta-wrapper {
		display: flex;
		flex-direction: row;
		width: 100%;
		align-items: center;
		justify-content: space-between;
	}
</style>
