<script>
    import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
	import ButtonLink from "./ButtonLink.svelte";

	export let leadTextColor = 'var(--shadow)';
	export let cardName = 'card name';
	export let subheading = 'subheading';
	export let imgPath = 'raver.jpg';
	export let desc = null;
	export let texts = [];
    export let price = "0";

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
		//backface.style.transform = `rotateY(${calcAngleX}deg) rotateX(${-calcAngleY}deg) scale(1.04) translateZ(-4px)`;

		const calcShadowX = (x - halfWidth) / 3;
		const calcShadowY = (y - halfHeight) / 6;
		//innerCard.style.filter = `drop-shadow(${calcShadowX}px ${calcShadowY}px 15px ${filterColor})`;
	}

	function resetCard() {
		card.classList.remove('animated');
		innerCard.style.transform = `rotateY(0deg) rotateX(0deg) scale(1)`;
		//backface.style.transform = `rotateY(0deg) rotateX(0deg) scale(1.01) translateZ(-4px)`;
		innerCard.style.filter = `drop-shadow(0 10px 15px ${filterColor})`;
	}

	function flipCard() {
		flipped = !flipped;
	}
</script>

<div class="ticket-wrapper">
<button
	class="card"
	bind:this={card}
	data-filter-color={filterColor}
	on:mouseenter={calculateAngle}
	on:mousemove={calculateAngle}
	on:mouseleave={resetCard}
	on:click={flipCard}
	style="--lead-text-color: {leadTextColor}"
>
	<div class="card-inner" bind:this={cardInner} class:flipped>
		<div class="inner-card" bind:this={innerCard}>
			<span class="glare"></span>
			<div class="circle"></div>
			<div class="circle"><p class="pp-supply">?</p></div>
			<div class="bg-image" style="background-image: url('/imgs/tickets/{imgPath}');"></div>
			<div class="texts-wrapper">
				<h1>{cardName}</h1>
				<p class="pp-supply">({subheading})</p>
			</div>
		</div>
		<div class="inner-card-backface" bind:this={backface}>
			<div class="circle"></div>
			<div class="circle"><p class="pp-supply" style="font-size: 50px;">&#10005;</p></div>
			<div class="ticket-detail">
				{#if desc}<p class="pp-supply desc">{desc}</p>{/if}
				{#each texts as programme}
					<div class="programme-day">
						<h3>{programme.label}</h3>
						{#each programme.texts as text}
							<p class="pp-supply">{text}</p>
						{/each}
					</div>
				{/each}
			</div>
		</div>
	</div>
</button>
<div class="cta">
    <h2>{price}</h2>
    <ButtonLink label="{langs[$lang].tickets.button}" href="https://goout.net/cs/dhogh-festival-2025/szjdaux/" marginAuto={false}/>
</div>
</div>

<style>
	:root {
		--lead-text-color: var(--shadow);
		--card-background: #0f0f0f;
	}

    .ticket-wrapper{
        display: flex;
        flex-direction: column;
    }

    .cta{
        padding-top: 1.5rem;
    }

    .cta h2{
        margin: 0;
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

	.card {
		all: unset;

		width: 370px;
		min-height: 530px;
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
		border-radius: 1rem;
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

	.circle {
		position: absolute;
		width: 30px;
		height: 30px;
		border-radius: 50%;
	}

	.circle:first-of-type {
		left: 50%;
		top: 5%;
		transform: translate(-50%, -50%);
		background-color: var(--blue);
		z-index: 10;
	}

	.circle:nth-of-type(2) {
		width: 35px;
		height: 35px;
		right: 5%;
		top: 4%;
		background-color: var(--card-background);
		color: var(--lead-text-color);
	}

	.circle p {
		color: var(--texts-color);
		font-size: 24px;
		margin: 0;
		padding: 0;
		position: absolute;
		left: 11px;
		top: 2px;
	}

	.inner-card-backface .circle:nth-of-type(2) {
		right: 7%;
		top: 0%;
	}

	.bg-image {
		border-radius: 0.5rem;
		min-height: 400px;
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

	.texts-wrapper h1,
	.texts-wrapper p {
		margin: 0;
		color: var(--lead-text-color);
	}

	.texts-wrapper p {
		font-size: var(--fs-16);
		line-height: 0.75rem;
		padding-bottom: 0.5rem;
	}
	.texts-wrapper h1 {
		font-size: var(--fs-54);
	}

	.ticket-detail {
		display: flex;
		flex-direction: column;
		justify-content: center;
		text-transform: uppercase;
		height: 100%;
		margin: 0 1rem;
	}

	.ticket-detail p {
		color: var(--shadow);
	}

	.programme-day h3 {
		margin: 0;
		padding-top: 1.5rem;
		color: var(--lead-text-color);
		border-bottom: 1px solid var(--shadow);
		margin-bottom: 0.8rem;
	}

	.programme-day p {
		margin: 0;
		line-height: 1.7rem;
	}

	.ticket-detail .desc {
		font-size: var(--fs-16);
		line-height: 1.2rem;
	}
</style>
