<script>
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import Heading from '$lib/Heading.svelte';
	import ArtistBlock from '$lib/ArtistBlock.svelte';
	import ButtonLink from '$lib/ButtonLink.svelte';
	import TicketPanel from '$lib/TicketPanel.svelte';

	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
	import BgImageContentBlock from '$lib/BgImageContentBlock.svelte';

	const eventLink = 'https://fb.me/e/gImSXNvsV';

	const ticketImgs = [
		'trueraver.jpg',
		'raver.jpg',
		'artists/humiks.jpg',
		'artists/alex.jpg',
		'artists/veitb.jpg'
	];
	const ticketLinks = [
		['https://fb.me/e/gImSXNvsV', 'https://fb.me/e/gImSXNvsV'],
		['https://fb.me/e/gImSXNvsV', 'https://fb.me/e/gImSXNvsV'],
		'https://fb.me/e/gImSXNvsV',
		'https://fb.me/e/gImSXNvsV',
		'https://fb.me/e/gImSXNvsV'
	];
</script>

<BgImageContentBlock imagePath="imgs/artists/veitb.jpg">
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
</BgImageContentBlock>

<ContentBlock backgroundColor="var(--blue)">
	<Heading heading="festival" />
	<div class="festival-content-wrapper">
		<div class="texts">
			{#each langs[$lang].festival as text}
				<p>{text}</p>
			{/each}
		</div>
		<div class="img-container"></div>
	</div>
</ContentBlock>

<BgImageContentBlock imagePath="imgs/values.jpg">
	<div class="values">
		<h1>{langs[$lang].values.label}</h1>
		{#each langs[$lang].values.values as value}
			<h2>{value.label}</h2>
			<p>{value.desc}</p>
		{/each}
	</div>
</BgImageContentBlock>

<ContentBlock backgroundColor="var(--green)">
	<Heading heading={langs[$lang].programme.label} />
	<div class="program-main-wrapper">
		<ArtistBlock name="Tigerhead (DE)" imgPath="veitb.jpg" />
		<ArtistBlock name="Alex Wilcox (US)" imgPath="alex.jpg" />
		<ArtistBlock name="Veit B" imgPath="veitb.jpg" />
		<ArtistBlock name="Mista Humiks" imgPath="humiks.jpg" />
		<ArtistBlock name="Alex Wilcox (US)" imgPath="alex.jpg" />
		<ArtistBlock name="Tigerhead (DE)" imgPath="veitb.jpg" />
		<ArtistBlock name="Mista Humiks" imgPath="humiks.jpg" />
		<ArtistBlock name="Veit B" imgPath="veitb.jpg" />
	</div>
	<div class="program-smaller-wrapper">
		<div class="wrapper">
			<h2>tigerhead (de)</h2>
			<h2>alex wilcox (us)</h2>
			<h2>veit b</h2>
			<h2>mista humiks</h2>
		</div>
		<div class="wrapper">
			<h2>alex wilcox (us)</h2>
			<h2>tigerhead (de)</h2>
			<h2>mista humiks</h2>
			<h2>veit b</h2>
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

<!-- <BgImageContentBlock imagePath="imgs/footer.jpg">
	<div class="footer">
		<ButtonLink label="facebook" href="https://www.facebook.com/DHOGHTEAM" marginAuto={false} />
		<ButtonLink label="instagram" href="https://www.instagram.com/dhoghteam/" marginAuto={false} />
		<ButtonLink label="dhoghteam@gmail.com" href="mailto:dhoghteam@gmail.com" marginAuto={false} />
	</div>
</BgImageContentBlock> -->

<style>
	.landing {
		position: absolute;
		width: 100vw;
		top: 40%;
	}

	.landing .content-wrapper {
		width: min-content;

		margin: auto;

		display: flex;
		flex-direction: column;
		align-items: center;
	}

	.landing .content-wrapper h1 {
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
		padding-right: var(--general-px);
	}

	.festival-content-wrapper .img-container {
		flex: 2;
		aspect-ratio: 1 / 1;
		background-image: url('/imgs/values.jpg');
		background-size: cover;
		background-position: center;
	}

	.values {
		margin: 0 calc(2 * var(--general-px));
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		align-content: space-around;
		height: 100%;
	}

	.values h1,
	.values h2,
	.values p {
		color: var(--shadow);
		background-color: var(--red);
		padding: 0.5rem;
	}

	.values p {
		margin: 0;
	}

	.values h2 {
		margin-bottom: 0;
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

	.program-smaller-wrapper .wrapper h2,
	.program-smaller-wrapper .wrapper h3,
	.program-smaller-wrapper .wrapper p {
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

		gap: 5rem 2rem;
		padding: calc(1.5 * var(--general-px));
	}

	.tickets-warning {
		text-transform: uppercase;
		color: var(--shadow);
		width: 100%;
		text-align: center;
		margin: 0;
		padding-bottom: 1rem;
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

	/* Small devices (phones, ≥576px) */
	@media (max-width: 767.98px) {
		.landing {
			top: 50%;
		}

		.landing .content-wrapper h1 {
			font-size: var(--fs-24);
		}

		.festival-content-wrapper {
			flex-direction: column;
		}

		.festival-content-wrapper .texts {
			padding: calc(0.5 * var(--general-px));
		}

		.values {
			margin: 0 calc(0.5 * var(--general-px));
		}

		.values h1 {
			font-size: var(--fs-20);
		}

		.values h2 {
			font-size: var(--fs-18);
		}

		.values p {
			font-size: var(--fs-12);
		}

		.program-main-wrapper {
			grid-template-columns: repeat(1, 1fr);
			padding: calc(0.5 * var(--general-px));
		}

		.program-smaller-wrapper {
			padding: calc(0.5 * var(--general-px));
			flex-direction: column;
			text-align: center;
		}

		.program-smaller-wrapper:last-of-type .wrapper h2:first-of-type {
			padding-bottom: 0;
		}

		.tickets-wrapper {
			padding: calc(0.5 * var(--general-px));
			grid-template-columns: repeat(1, 1fr);
			/* grid-template-rows: repeat(5, auto); */
		}
	}

	/* Medium devices (tablets, ≥768px) */
	@media (min-width: 768px) and (max-width: 991.98px) {
		/* Styles for tablets */
	}

	/* Large devices (desktops, ≥992px) */
	@media (min-width: 992px) and (max-width: 1199.98px) {
		/* Styles for small desktops */
	}

	/* Extra large devices (large desktops, ≥1200px) */
	@media (min-width: 1200px) {
		/* Styles for large screens */
	}
</style>
