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

<svelte:head>
	<script type="application/ld+json">
		{
			"@context": "https://schema.org",
			"@type": "Festival",
			"name": "DHOGH Festival 2025",
			"startDate": "2025-06-18",
			"endDate": "2025-06-20",
			"location": {
				"@type": "Place",
				"name": "Žižkárna",
				"url": "https://zizkarna.cz",
				"address": {
					"@type": "PostalAddress",
					"streetAddress": "Žižkova tř. 28",
					"addressLocality": "České Budějovice",
					"addressCountry": "CZ"
				}
			},
			"description": "Festival propojuje taneční hudbu, umění, filozofii a komunitního ducha undergroundové scény. Poskytuje nejen kulturní zážitek, ale i prostor pro hlubší reflexi nad významem elektronické hudby a jejího vlivu na městský noční život.",
			"eventSchedule": [
				{
					"@type": "Event",
					"name": "Středa - Local DJs, Ableton Workshop, DJ Workshop",
					"startDate": "2025-06-18",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "MusicGroup",
							"name": "body_bass"
						},
						{
							"@type": "Person",
							"name": "antonin_padrta"
						},
						{
							"@type": "Event",
							"name": "DJ Workshop"
						}
					]
				},
				{
					"@type": "Event",
					"name": "Čtvrtek - Live Sets, Synth Workshop",
					"startDate": "2025-06-19",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "MusicGroup",
							"name": "Jadran"
						},
						{
							"@type": "Person",
							"name": "mista_humix"
						},
						{
							"@type": "MusicGroup",
							"name": "BIOTOP"
						},
						{
							"@type": "Person",
							"name": "Tom_Holič"
						},
						{
							"@type": "Organization",
							"name": "Synth Library Prague"
						}
					]
				},
				{
					"@type": "Event",
					"name": "Pátek - Open Air (17:00-22:00)",
					"startDate": "2025-06-20T17:00",
					"endDate": "2025-06-20T22:00",
					"location": {
						"@type": "Place",
						"name": "Žižkárna",
						"url": "https://zizkarna.cz",
						"address": {
							"@type": "PostalAddress",
							"streetAddress": "Žižkova tř. 28",
							"addressLocality": "České Budějovice",
							"addressCountry": "CZ"
						}
					},
					"performer": [
						{
							"@type": "Person",
							"name": "TIGERHEAD",
							"sameAs": "https://ra.co/dj/tigerhead"
						},
						{
							"@type": "Person",
							"name": "ALEX_WILCOX",
							"sameAs": "https://www.discogs.com/artist/8125675-Alex-Wilcox"
						},
						{
							"@type": "Person",
							"name": "WNCHNZ"
						},
						{
							"@type": "Person",
							"name": "Surrealita",
							"sameAs": "https://ra.co/dj/surrealita"
						},
						{
							"@type": "Person",
							"name": "Dj_Alyaz",
							"sameAs": "https://ra.co/dj/djalyaz"
						},
						{
							"@type": "Person",
							"name": "Mor4m"
						},
						{
							"@type": "Person",
							"name": "VEIT B",
							"sameAs": "https://soundcloud.com/veit-b"
						},
						{
							"@type": "Person",
							"name": "tvyks"
						}
					]
				}
			],
			"offers": [
				{
					"@type": "Offer",
					"name": "Full Festival Pass",
					"description": "Vstupenka na všechny festivalové dny včetně páteční afterparty",
					"price": "500",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				},
				{
					"@type": "Offer",
					"name": "Friday Open Air",
					"description": "Vstupenka na páteční program na hlavní stage, kde vystoupí oba headlineři",
					"price": "300",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				},
				{
					"@type": "Offer",
					"name": "Wormuper (Středa/Čtvrtek)",
					"description": "Vstupenka na středeční a čtvrteční program zaměřený na vzdělávání a komunitu",
					"price": "100-200",
					"priceCurrency": "CZK",
					"availability": "https://schema.org/InStock",
					"url": "https://goout.net/cs/dhogh-festival-2025/szjdaux/"
				}
			],
			"organizer": {
				"@type": "Organization",
				"name": "DHOGH Team",
				"email": "dhoghteam@gmail.com",
				"url": "https://dhogh.com"
			},
			"image": [
				"https://dhogh.com/imgs/artists/alex.jpg",
				"https://dhogh.com/imgs/artists/tigerhead.jpg",
				"https://dhogh.com/imgs/artists/wnchnz.jpg",
				"https://dhogh.com/imgs/values.jpg"
			],
			"url": "https://dhogh.com"
		}
	</script>
</svelte:head>

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
				<ProgrammeDay programme={day} color={ticketColors[i]} />
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
	headingSvg="2"
	topSvg={null}
>
<p class="flip">{langs[$lang].tickets.flip}</p>
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

	.flip{
		text-align: center;
		color: var(--shadow);
		padding-bottom: 5rem;
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
