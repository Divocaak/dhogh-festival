<script>
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import Heading from '$lib/Heading.svelte';
	import ArtistBlock from '$lib/ArtistBlock.svelte';
	import ButtonLink from '$lib/ButtonLink.svelte';
	import TicketPanel from '$lib/TicketPanel.svelte';

	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';

	const eventLink = 'https://fb.me/e/gImSXNvsV';

	const ticketImgs = ['/tst.jpg', '/tst.jpg', '/tst.jpg', '/tst.jpg', '/tst.jpg'];
	const ticketLinks = [
		['https://fb.me/e/gImSXNvsV', 'https://fb.me/e/gImSXNvsV'],
		['https://fb.me/e/gImSXNvsV', 'https://fb.me/e/gImSXNvsV'],
		'https://fb.me/e/gImSXNvsV',
		'https://fb.me/e/gImSXNvsV',
		'https://fb.me/e/gImSXNvsV'
	];
</script>

<ContentBlock>
	<InfoBlock />
	<div class="landing">
		<div class="content-wrapper">
			{#each langs[$lang].landing.texts as text}
				<h1>{text}</h1>
			{/each}
			<div class="buttons-wrapper">
				<ButtonLink
					link={eventLink}
					label="event"
					bgColor="var(--shadow)"
					txtColor="var(--black)"
					marginAuto={false}
				/>
				<ButtonLink
					link=""
					label="tickets"
					bgColor="var(--shadow)"
					txtColor="var(--black)"
					marginAuto={false}
				/>
			</div>
		</div>
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--blue)">
	<Heading heading="festival" />
	<div class="festival-content-wrapper">
		<div class="texts">
			{#each langs[$lang].festival as text}
				<p>{text}</p>
			{/each}
		</div>
		<div class="img-container">
			<img src="/tst.jpg" alt="" />
		</div>
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--green)">
	<Heading heading={langs[$lang].programme.label} />
	<div class="program-main-wrapper">
		<ArtistBlock name="Tigerhead (DE)" />
		<ArtistBlock name="Alex Wilcox (US)" />
		<ArtistBlock />
		<ArtistBlock />
		<ArtistBlock />
		<ArtistBlock />
		<ArtistBlock />
		<ArtistBlock />
	</div>
	<div class="program-smaller-wrapper">
		<div class="wrapper">
			<h2>1. artist name</h2>
			<h2>2. artist name</h2>
			<h2>3. artist name</h2>
			<h2>4. artist name</h2>
		</div>
		<div class="wrapper">
			<h2>5. artist name</h2>
			<h2>6. artist name</h2>
			<h2>7. artist name</h2>
			<h2>8. artist name</h2>
		</div>
	</div>
	<div class="program-smaller-wrapper">
		<div class="wrapper">
			<h2>{langs[$lang].programme.workshops.label}</h2>
			{#each langs[$lang].programme.workshops.texts as text}
				<h3>{text}</h3>
			{/each}
		</div>
		<div class="wrapper">
			<h2>{langs[$lang].programme.discussions.label}</h2>
			{#each langs[$lang].programme.discussions.texts as text}
				<h3>{text.label}</h3>
				<p>{text.desc}</p>
			{/each}
		</div>
	</div>
	<div class="button-wrapper">
		<ButtonLink href={eventLink} label="event" />
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--violet)">
	<Heading heading={langs[$lang].tickets.label} />
	<div class="tickets-wrapper">
		{#each langs[$lang].tickets.tickets as ticket, i}
			<TicketPanel
				label={ticket.label}
				desc={ticket.desc}
				texts={ticket.texts}
				imgPath={ticketImgs[i]}
				price={ticket.price}
				link={ticketLinks[i] instanceof Array ? ticketLinks[i][0] : ticketLinks[i]}
				priceSecondWave={ticket.priceSecondWave}
				linkSecondWave={ticketLinks[i] instanceof Array ? ticketLinks[i][1] : ticketLinks[i]}
				twoCols={langs[$lang].tickets.tickets.length - 1 == i && i % 2 == 0}
			/>
		{/each}
	</div>
	<p class="tickets-warning">lístky platné pouze nákupem v síti goout</p>
</ContentBlock>
<ContentBlock>
	<div class="footer">
		<ButtonLink label="facebook" href="https://www.facebook.com/DHOGHTEAM" marginAuto={false} />
		<ButtonLink label="instagram" href="https://www.instagram.com/dhoghteam/" marginAuto={false} />
		<ButtonLink label="dhoghteam@gmail.com" href="mailto:dhoghteam@gmail.com" marginAuto={false} />
	</div>
</ContentBlock>

<style>
	.landing {
		position: absolute;
		width: 100%;
		top: 40%;
	}

	.landing .content-wrapper {
		width: max-content;

		margin: auto;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.landing h1 {
		background-color: var(--peach);
		width: max-content;
		padding: 0.3rem 1.5rem;
		margin: 0;
	}

	.landing .content-wrapper .buttons-wrapper {
		display: flex;
		flex-direction: row;
		width: 100%;
		justify-content: space-between;
		padding-top: 3rem;
	}

	.festival-content-wrapper {
		display: flex;
		flex-direction: row;
	}

	.festival-content-wrapper .texts {
		flex: 3;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding-left: calc(2 * var(--general-px));
	}

	.festival-content-wrapper .img-container {
		flex: 2;
		aspect-ratio: 1 / 1;
		background-image: url('tst.jpg');
		background-size: cover;
		background-position: center;
	}

	img {
		position: relative;
		height: 100%;
		width: 100%;
	}

	.program-main-wrapper {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		grid-template-rows: repeat(2, auto);
		gap: 2rem;
		padding: calc(2 * var(--general-px));
		padding-bottom: 0;
	}

	.program-smaller-wrapper {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		padding: 0 calc(2 * var(--general-px));
		padding-top: var(--general-px);
	}

	.program-smaller-wrapper .wrapper {
		width: 100%;
	}

	.program-smaller-wrapper .wrapper h2 {
		color: var(--shadow);
	}

	.program-smaller-wrapper:last-of-type .wrapper h2:first-of-type {
		padding-bottom: 2rem;
	}

	.button-wrapper {
		width: 100%;
		padding: 7rem 0;
	}

	.tickets-wrapper {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		grid-template-rows: repeat(3, auto);

		gap: 2rem;
		padding: calc(1.5 * var(--general-px));
	}

	.tickets-warning {
		text-transform: uppercase;
		color: var(--shadow);
		width: 100%;
		text-align: center;
		margin: 0;
	}

	.footer {
		display: flex;
		flex-direction: row;
		position: absolute;
		width: 100%;
		justify-content: space-evenly;
		margin: auto;
		bottom: 10%;
	}
</style>
