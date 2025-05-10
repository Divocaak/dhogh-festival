<script>
	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import ButtonLink from '$lib/ButtonLink.svelte';
	import BgImageContentBlock from '$lib/BgImageContentBlock.svelte';
	import TicketCard from '$lib/TicketCard.svelte';
	import Footer from '$lib/Footer.svelte';
	import ProgrammeCard from '$lib/ProgrammeCard.svelte';
	import SupportArtist from '$lib/SupportArtist.svelte';

	const ticketColors = ['var(--red)', 'var(--violet)', 'var(--green)'];
</script>

<BgImageContentBlock imagePath="imgs/artists/veitb.jpg">
	<svg
		width="1512"
		height="138"
		viewBox="0 0 1512 138"
		xmlns="http://www.w3.org/2000/svg"
		class="landing-svg"
	>
		<path d="M1036.65 88.2131L945.187 88.2131L945.187 138L1036.65 138L1036.65 88.2131Z" />
		<path d="M1295.97 60.6909L1036.65 60.6909L1036.65 88.562L1295.97 88.562L1295.97 60.6909Z" />
		<path d="M1347.18 18.9513L1295.77 18.9513L1295.77 60.5566L1347.18 60.5566L1347.18 18.9513Z" />
		<path
			d="M1376.85 -9.61711L1347.16 -9.61711L1347.16 18.9515L1376.85 18.9515L1376.85 -9.61711Z"
		/>
		<path d="M1467.97 18.9513L1376.86 18.9513L1376.86 88.1864L1467.97 88.1864L1467.97 18.9513Z" />
		<path d="M1519.42 88.1864L1467.97 88.1864L1467.98 129.953L1519.42 129.953L1519.42 88.1864Z" />
		<path d="M1611.66 63.8828L1519.4 63.8828L1519.4 88.1593L1611.66 88.1593L1611.66 63.8828Z" />
		<path d="M1701.86 20.4801L1611.65 20.4801L1611.65 63.8828L1701.86 63.8828L1701.86 20.4801Z" />
		<path d="M1611.8 -51.8397L1376.63 -51.8397L1376.63 -9.32211L1611.8 -9.3221L1611.8 -51.8397Z" />
		<path d="M1702 -80.7031L1611.8 -80.7031L1611.8 -51.8127L1702 -51.8127L1702 -80.7031Z" />
		<path
			d="M1295.72 -53.5831L1205.85 -53.5831L1205.85 19.4074L1295.72 19.4074L1295.72 -53.5831Z"
		/>
		<path
			d="M1123.75 -10.1268L863.484 -10.1268L863.484 18.8441L1123.75 18.8441L1123.75 -10.1268Z"
		/>
		<path
			d="M1123.58 -122.148L1033.78 -122.148L1033.78 -50.3104L1123.58 -50.3104L1123.58 -122.148Z"
		/>
		<path d="M1175.48 -50.2837L1123.75 -50.2837L1123.75 -10.1L1175.48 -10.1L1175.48 -50.2837Z" />
		<path
			d="M175.364 -128.451L-85.1857 -128.451L-85.1857 -81.7761L175.364 -81.7761L175.364 -128.451Z"
		/>
		<path
			d="M372.052 -128.479L268.927 -128.479L268.927 -51.5717L372.052 -51.5717L372.052 -128.479Z"
		/>
		<path
			d="M561.745 0.120022L268.943 0.120009L268.943 34.0803L561.745 34.0803L561.745 0.120022Z"
		/>
		<path
			d="M268.944 -51.5714L208.63 -51.5714L208.63 0.120128L268.943 0.120009L268.944 -51.5714Z"
		/>
		<path
			d="M208.613 -81.8031L175.364 -81.8031L175.364 -51.5981L208.613 -51.5981L208.613 -81.8031Z"
		/>
		<path
			d="M175.364 -51.5714L75.4319 -51.5715L75.4319 32.6051L175.364 32.6051L175.364 -51.5714Z"
		/>
		<path d="M75.3981 32.6318L15.7938 32.6318L15.7938 72.6275L75.3981 72.6275L75.3981 32.6318Z" />
		<path d="M15.7936 4.78774L-85.1857 4.78773L-85.1857 32.6051L15.7936 32.6051L15.7936 4.78774Z" />
		<path
			d="M-85.1856 -51.5715L-189.983 -51.5715L-189.983 4.78773L-85.1857 4.78773L-85.1856 -51.5715Z"
		/>
		<path d="M-85.2024 -174L-190 -174L-190 -128.478L-85.2024 -128.478L-85.2024 -174Z" />
	</svg>
	<InfoBlock />
</BgImageContentBlock>

<!-- <ContentBlock backgroundColor="var(--grey)" heading={langs[$lang].artists.label}>
	<div class="artists-wrapper">
		{#each langs[$lang].artists.headliners as artist}
			<ProgrammeCard cardName={artist.name} imgPath={artist.img} desc={artist.desc} />
		{/each}
		{#each langs[$lang].artists.supporters as artist}
			<SupportArtist name={artist} />
		{/each}
	</div>
</ContentBlock>
<ContentBlock
	backgroundColor="var(--grey)"
	heading={langs[$lang].education.label}
	headingSvg="1"
	topSvg={null}
>
	<div class="artists-wrapper">
		{#each langs[$lang].education.events as event}
			<ProgrammeCard cardName={event.name} imgPath={event.img} desc={event.desc} />
		{/each}
	</div>
</ContentBlock> -->
<ContentBlock backgroundColor="var(--green)" heading="festival">
	<div class="festival-content-wrapper">
		<p>{langs[$lang].festival[0]}</p>
		<img src="/imgs/artists/veitb.jpg" alt="about" />
	</div>
	<div class="festival-content-wrapper">
		<img src="/imgs/values.jpg" alt="mission" />
		<p>{langs[$lang].festival[1]}</p>
	</div>
	<div class="values-wrapper">
		{#each langs[$lang].values.values as value}
			<div class="value">
				<h2>{value.label}</h2>
				<p>{value.desc}</p>
			</div>
		{/each}
	</div>
</ContentBlock>
<ContentBlock
	backgroundColor="var(--blue)"
	heading="{langs[$lang].tickets.label}"
	headingClr="var(--black)"
	headingBgClr="var(--shadow)"
	headingSvg="1"
>
	<div class="tickets-wrapper" id="tickets">
		{#each langs[$lang].tickets.tickets as ticket, i}
			<TicketCard
				leadTextColor={ticketColors[i]}
				cardName={ticket.label}
				subheading={ticket.subheading}
				imgPath={ticket.img}
				desc={ticket.desc}
				texts={ticket.texts}
				price={ticket.price}
			/>
		{/each}
	</div>
	<Footer />
</ContentBlock>

<style>
	.landing-svg {
		position: absolute;
		fill: var(--green);
		width: 100%;
	}

	.festival-content-wrapper {
		display: flex;
		flex-direction: row;

		gap: 3rem;
		justify-content: center;
		align-items: start;

		padding: 1.5rem 0;
	}

	.festival-content-wrapper p {
		width: 570px;
		margin: 0;
	}

	.festival-content-wrapper img {
		width: 570px;
		height: auto;
	}

	.values-wrapper {
		padding: 10rem 0;
		display: flex;
		flex-direction: row;
		justify-content: center;
		gap: 3rem;
	}

	.value {
		display: flex;
		flex-direction: column;
		width: 380px;
	}

	.value p {
		font-size: var(--fs-20);
		margin: 0;
	}

	.value h2 {
		margin: 0;
	}

	.artists-wrapper {
		display: grid;
		grid-template-columns: repeat(4, 1fr);

		gap: 5rem 2rem;
		padding: calc(1.5 * var(--general-px));
	}

	.tickets-wrapper {
		display: grid;
		grid-template-columns: repeat(3, 1fr);

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

	/* Small devices (phones, ≥576px) */
	@media (max-width: 1200px) {
		.festival-content-wrapper {
			flex-direction: column;
		}

		.festival-content-wrapper:nth-of-type(2) {
			flex-direction: column-reverse;
		}

		.festival-content-wrapper p {
			width: calc(100% - 2 * 3rem);
			padding: 0 3rem;
		}

		.festival-content-wrapper img {
			width: 100%;
		}

		.values-wrapper {
			flex-direction: column;
		}

		.value {
			width: calc(100% - 6rem);
			padding: 0 3rem;
		}

		.tickets-wrapper {
			padding: 0;
			display: flex;
			flex-direction: column;
		}

		.artists-wrapper {
			display: flex;
			flex-direction: column;
			align-items: center;
			padding: 0;
		}

		.artists-wrapper:last-of-type {
			padding-bottom: 10rem;
		}
	}
</style>
