<script>
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import Heading from '$lib/Heading.svelte';
	import ArtistBlock from '$lib/ArtistBlock.svelte';
	import Button from '$lib/Button.svelte';
	import TicketPanel from '$lib/TicketPanel.svelte';

	const eventLink = 'https://fb.me/e/gImSXNvsV';
	const trueRaverTicketLink = 'https://fb.me/e/gImSXNvsV';
	const raverTicketLink = 'https://fb.me/e/gImSXNvsV';
</script>

<ContentBlock>
	<InfoBlock />
	<div class="landing">
		<div>
			<h1>3 dny elektronické hudby</h1>
			<h1>15 interpretů</h1>
			<h1>+ workshopy a diskuze</h1>
		</div>
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--blue)">
	<Heading heading="festival" />
	<div class="festival-content-wrapper">
		<div class="texts">
			<p>
				Festival propojuje taneční hudbu, umění, filozofii a komunitního ducha undergroundové scény.
				Poskytuje nejen kulturní zážitek, ale i prostor pro hlubší reflexi nad významem elektronické
				hudby a jejího vlivu na městský noční život.
			</p>
			<p>
				Festival propojuje taneční hudbu, umění, filozofii a komunitního ducha undergroundové scény.
				Poskytuje nejen kulturní zážitek, ale i prostor pro hlubší reflexi nad významem elektronické
				hudby a jejího vlivu na městský noční život.
			</p>
		</div>
		<div class="img-container">
			<img src="/tst.jpg" alt="" />
		</div>
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--green)">
	<Heading heading="program" />
	<div class="program-main-wrapper">
		<ArtistBlock />
		<ArtistBlock />
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
			<h2>workshopy</h2>
			<h2>ws name</h2>
			<h2>ws name</h2>
		</div>
		<div class="wrapper">
			<h2>diskuze</h2>
			<h2>label</h2>
			<h2>label</h2>
			<h2>label</h2>
		</div>
	</div>
	<div class="button-wrapper">
		<Button href={eventLink} label="event" />
	</div>
</ContentBlock>
<ContentBlock backgroundColor="var(--violet)">
	<Heading heading="lístky" />
	<div class="tickets-wrapper">
		<TicketPanel
			label="true raver"
			desc="full festival pass"
			descLong="Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur."
			imgPath="/tst.jpg"
			price="450"
			link={trueRaverTicketLink}
		/>
		<TicketPanel
			label="raver"
			desc="friday main stage only"
			descLong="Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Quis autem vel eum iure reprehenderit qui in ea voluptate velit esse quam nihil molestiae consequatur."
			imgPath="/tst.jpg"
			price="300"
			link={raverTicketLink}
		/>
	</div>
    <p class="tickets-warning">lístky platné pouze nákupem v síti goout</p>
</ContentBlock>

<style>
	.landing {
		position: relative;
		width: 100%;
		top: 40%;
	}

	.landing div {
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

	.festival-content-wrapper {
		display: flex;
		flex-direction: row;
		align-items: center;
	}

	.festival-content-wrapper .texts {
		background-color: red;
		width: 60%;
		margin: 10rem;
	}

	.festival-content-wrapper .img-container {
		position: relative;
		width: 40%;
		height: 100%;
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
		display: flex;
		flex-direction: row;
        justify-content: center;
        gap: 2rem;
        align-content: center;
        padding: calc(1.5 * var(--general-px));
	}

    .tickets-warning{
        text-transform: uppercase;
        color: var(--shadow);
        width: 100%;
        text-align: center;
    }
</style>
