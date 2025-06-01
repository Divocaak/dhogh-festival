<script>
	import { lang } from '$lib/stores/LangStore.js';
	import langs from '$lib/localization.json';
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ButtonLink from '$lib/ButtonLink.svelte';
	import TicketCard from '$lib/TicketCard.svelte';
	import Footer from '$lib/Footer.svelte';
	import Artist from '$lib/Artist.svelte';
	import ProgrammeDay from '$lib/ProgrammeDay.svelte';
	import Value from '$lib/Value.svelte';
	import Button from '$lib/Button.svelte';

	const ticketColors = ['var(--red)', 'var(--violet)', 'var(--green)'];
</script>

<div class="lang-btn-wrapper">
	<Button
		label={$lang === 'cs' ? 'en' : 'cz'}
		onclick={() => lang.set($lang === 'cs' ? 'en' : 'cs')}
		marginAuto={false}
	/>
</div>

<ContentBlock backgroundColor="var(--grey)" topSvg={null}>
	<InfoBlock />
	<div class="artists-wrapper">
		<Artist name="tigerhead" imgPath="tigerhead.jpg"></Artist>
		<Artist name="alex_wilcox" imgPath="alex.jpg"></Artist>
		<Artist name="wnchnz" imgPath="wnchnz.jpg"></Artist>
	</div>
	<div class="programme-wrapper">
		<div class="event-btn-wrapper">
			<ButtonLink href="https://fb.me/e/gImSXNvsV" label="event" isEvent={true} />
		</div>
		<div class="programme">
			{#each langs[$lang].programme as day, i}
				<ProgrammeDay label={day.label} artists={day.artists} color={ticketColors[i]} />
			{/each}
		</div>
	</div>
</ContentBlock>

<ContentBlock backgroundColor="var(--green)" heading="festival">
	<div class="festival-wrapper">
		<img src="/imgs/values.jpg" alt="about festival" />
		<div class="festival-texts-wrapper">
			{#each langs[$lang].festival as text}
				<p>{text}</p>
			{/each}
		</div>
	</div>
	<div class="values-wrapper">
		{#each langs[$lang].values.values as value}
			<Value {value} />
		{/each}
	</div>
</ContentBlock>

<ContentBlock
	backgroundColor="var(--green)"
	heading={langs[$lang].tickets.label}
	headingSvg="1"
	topSvg={null}
>
	<div class="tickets-wrapper" id="tickets">
		{#each langs[$lang].tickets.tickets as ticket, i}
			<TicketCard leadTextColor={ticketColors[i]} {ticket} />
		{/each}
	</div>
</ContentBlock>

<ContentBlock backgroundColor="var(--grey)" headingSvg={null} topSvg={1}>
	<Footer />
</ContentBlock>

<style>
	.lang-btn-wrapper {
		position: absolute;
		width: 100%;
		top: 0;
		display: flex;
		flex-direction: row-reverse;
		z-index: 10;
	}

	.artists-wrapper,
	.programme-wrapper,
	.festival-wrapper,
	.values-wrapper {
		display: flex;
		flex-direction: row;

		gap: 1rem;
		padding: 0 var(--general-px);
	}

	.programme-wrapper {
		margin-top: 2rem;
	}

	.programme-wrapper .event-btn-wrapper {
		flex: 1;
	}

	.programme-wrapper .programme {
		flex: 2;
	}

	.festival-wrapper {
		gap: 3rem;
		justify-content: center;
		align-items: start;
	}

	.festival-texts-wrapper {
		display: flex;
		flex-direction: column;
	}

	.festival-wrapper p {
		width: 570px;
		margin: 0;
		border-top: 2px solid var(--black);
		padding: 4rem 0;
		font-size: var(--fs-20);
	}

	.festival-wrapper img {
		width: 570px;
		height: auto;
	}

	.values-wrapper {
		padding-top: 10rem;
		justify-content: center;
		gap: 5rem;
	}

	.tickets-wrapper {
		display: grid;
		grid-template-columns: repeat(3, 1fr);

		gap: 5rem 2rem;
		padding: 0 var(--general-px);
	}

	/* Small devices (phones, ≥576px) */
	@media (max-width: 1200px) {
		.lang-btn-wrapper {
			position: relative;
		}

		.artists-wrapper,
		.programme-wrapper,
		.festival-wrapper,
		.values-wrapper {
			flex-direction: column;
			padding: 0 var(--general-px-sm);
		}

		.programme-wrapper {
			gap: 3rem;
		}

		.festival-wrapper img,
		.festival-wrapper p {
			width: 100%;
		}

		.values-wrapper {
			padding-top: 5rem;
		}

		.tickets-wrapper {
			display: flex;
			flex-direction: column;
			padding: 0;
		}
	}
</style>
