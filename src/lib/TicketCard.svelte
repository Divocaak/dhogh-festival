<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import ButtonLink from './ButtonLink.svelte';
	import FlippingCard from './FlippingCard.svelte';

	export let leadTextColor = 'var(--shadow)';
	export let ticket;
</script>

<div class="ticket-wrapper" style="--lead-text-color:{leadTextColor}">
	<FlippingCard>
		<div slot="inner" class="inner">
			<div class="circle"></div>
			<div class="bg-image" style="background-image: url('/imgs/tickets/{ticket.img}');"></div>
			<div class="texts-wrapper">
				<h1>{ticket.label}</h1>
				<p class="pp-supply">({ticket.subheading})</p>
			</div>
		</div>
		<div slot="backface" class="backface">
			<div class="circle"></div>
			<div class="ticket-detail">
				{#if ticket.desc}<p class="pp-supply desc">{ticket.desc}</p>{/if}
				{#each ticket.texts as programme}
					<div class="programme-day">
						<h3>{programme.label}</h3>
						{#each programme.texts as text}
							<p class="pp-supply">{text}</p>
						{/each}
					</div>
				{/each}
			</div>
		</div>
	</FlippingCard>
	<div class="cta">
		<h2>{ticket.price}</h2>
		<ButtonLink
			label={langs[$lang].tickets.button}
			href="https://goout.net/cs/dhogh-festival-2025/szjdaux/"
			marginAuto={false}
		/>
	</div>
	<p class="ticket-text">{ticket.text}</p>
</div>

<style>
	:root {
		--lead-text-color: var(--shadow);
		--card-background: var(--black);
	}

	.inner,
	.backface {
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
	}

	.ticket-wrapper {
		display: flex;
		flex-direction: column;
	}

	.cta {
		padding: 2rem 0;
	}

	.cta h2 {
		margin: 0;
	}

	.circle {
		position: absolute;
		width: 30px;
		height: 30px;
		border-radius: 50%;
		left: 50%;
		top: 5%;
		transform: translate(-50%, -50%);
		background-color: var(--blue);
		z-index: 10;
	}

	.bg-image {
		border-radius: calc(var(--card-border-radius) / 2);
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

	.ticket-text {
		color: var(--shadow);
		font-size: var(--fs-20);
		width: 90%;
	}

	@media (max-width: 1200px) {
		.texts-wrapper h1 {
			font-size: var(--fs-48);
		}

		.texts-wrapper p {
			font-size: var(--fs-14);
		}

		.ticket-wrapper {
			width: calc(100% - 3rem);
			padding: 0 1.5rem;
		}
	}
</style>
