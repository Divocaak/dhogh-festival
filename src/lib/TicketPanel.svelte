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
	<div class="img" style="background-image: url('/imgs/{imgPath}');"></div>
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
				<p>{price}</p>
				<ButtonLink label="koupit" href={link} marginAuto={false} smallerPaddings={true} />
			</div>
			{#if priceSecondWave}
				<div class="cta-wrapper">
					<p>{priceSecondWave}</p>
					<ButtonLink
						label="koupit"
						href={linkSecondWave}
						marginAuto={false}
						smallerPaddings={true}
					/>
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

	h1 {
		font-size: var(--fs-24);
	}

	h2 {
		font-size: var(--fs-20);
	}

	p {
		font-size: var(--fs-14);
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
		background-size: cover;
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

	.texts .texts-wrapper:last-of-type {
		padding-top: 3rem;
	}

	.cta-wrapper {
		display: flex;
		flex-direction: row;
		width: 100%;
		align-items: center;
		justify-content: space-between;
	}

	.cta-wrapper:nth-child(2) {
		padding-top: 0.2rem;
	}
</style>
