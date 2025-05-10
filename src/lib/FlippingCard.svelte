<script>
	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
	import ButtonLink from './ButtonLink.svelte';

	export let widthPx = '370px';
	export let minHeightPx = '530px';
	export let minHeightPxSm = '530px';

	let card;
	let cardInner;
	let innerCard;
	let backface;

	const filterColor = 'rgba(0, 0, 0, 0.3)';
	let flipped = false;

	function calculateAngle(e) {
		if (!card || !innerCard || !backface) return;

		card.classList.add('animated');

		const rect = innerCard.getBoundingClientRect();
		const x = Math.abs(rect.x - e.clientX);
		const y = Math.abs(rect.y - e.clientY);
		const halfWidth = rect.width / 2;
		const halfHeight = rect.height / 2;

		const calcAngleX = (x - halfWidth) / 12;
		const calcAngleY = (y - halfHeight) / 28;
		const gX = (1 - x / (halfWidth * 2)) * 100;
		const gY = (1 - y / (halfHeight * 2)) * 100;

		//rgba(199 198 243)
		//innerCard.querySelector('.glare').style.background =
		`radial-gradient(circle at ${gX}% ${gY}%, rgba(255 255 255), transparent)`;

		const perspective = `${halfWidth * 6}px`;
		card.style.perspective = perspective;
		innerCard.style.perspective = perspective;

		innerCard.style.transform = `rotateY(${-calcAngleX}deg) rotateX(${calcAngleY}deg) scale(1.04)`;
		//backface.style.transform = `rotateY(${-calcAngleX}deg) rotateX(${calcAngleY}deg) scale(1.04) translateZ(-4px)`;

		const calcShadowX = (x - halfWidth) / 3;
		const calcShadowY = (y - halfHeight) / 6;
		//innerCard.style.filter = `drop-shadow(${calcShadowX}px ${calcShadowY}px 15px ${filterColor})`;
	}

	function resetCard() {
		card.classList.remove('animated');
		innerCard.style.transform = `rotateY(0deg) rotateX(0deg) scale(1)`;
		//backface.style.transform = `rotateY(0deg) rotateX(0deg) scale(1.01) translateZ(-4px)`;
		//innerCard.style.filter = `drop-shadow(0 10px 15px ${filterColor})`;
	}

	function flipCard() {
		flipped = !flipped;
	}
</script>

<button
	class="card"
	bind:this={card}
	data-filter-color={filterColor}
	on:mouseenter={calculateAngle}
	on:mousemove={calculateAngle}
	on:mouseleave={resetCard}
	on:click={flipCard}
	style="--width:{widthPx}; --min-height:{minHeightPx}; --min-height-sm:{minHeightPxSm}"
>
	<div class="card-inner" bind:this={cardInner} class:flipped>
		<div class="inner-card" bind:this={innerCard}>
			<span class="glare"></span>
			<div class="circle"><p class="pp-supply">?</p></div>
			<slot name="inner"></slot>
		</div>
		<div class="inner-card-backface" bind:this={backface}>
			<div class="circle cross"><p class="pp-supply">&#10005;</p></div>
			<slot name="backface"></slot>
		</div>
	</div>
</button>

<style>
	:root {
		--width: 370px;
		--min-height: 530px;
		--min-height-sm: 500px;
		--card-background: var(--black);
	}

	.glare {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		left: 0;
		pointer-events: none;
		z-index: 1;
	}

	.circle {
		position: absolute;
		border-radius: 50%;
		width: 35px;
		height: 35px;
		right: 3%;
		top: 3%;
		background-color: var(--card-background);
	}

	.circle p {
		color: var(--lead-text-color);
		font-size: 24px;
		margin: 0;
		padding: 0;
		position: absolute;
		left: 11px;
		top: 2px;
	}

	.circle.cross p {
		left: 0;
		top: -15px;
		font-size: 50px;
	}

	.card {
		all: unset;

		width: var(--width);
		min-height: var(--min-height);
		height: auto;
		perspective: 1000px;
		cursor: pointer;

		transform-style: preserve-3d;
	}

	.card-inner {
		position: relative;
		width: 100%;
		height: 100%;
		transform-style: preserve-3d;
		transition: transform 0.6s ease;
	}

	.card-inner.flipped {
		transform: rotateY(180deg);
	}

	.inner-card,
	.inner-card-backface {
		position: absolute;
		width: 100%;
		height: 100%;
		backface-visibility: hidden;
		border-radius: var(--card-border-radius);
		overflow: hidden;
		padding: 0.75rem;
		box-sizing: border-box;

		background-color: var(--card-background);
	}

	.inner-card {
		display: flex;
		flex-direction: column;
		z-index: 2;
	}

	.inner-card-backface {
		transform: rotateY(180deg);
	}

	@media (max-width: 1200px) {
		.card {
			height: var(--min-height-sm);
			width: 100%;
		}
	}
</style>
