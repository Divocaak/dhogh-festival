<script>
	import InfoBlock from '$lib/InfoBlock.svelte';
	import ContentBlock from '$lib/ContentBlock.svelte';
	import Heading from '$lib/Heading.svelte';
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
<ContentBlock padded={true} backgroundColor="var(--blue)">
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
        /* overflow: hidden; */
		width: 40%;
		height: 100%;
	}


	img {
		position: relative;
        height: 100%;
        width: 100%;
	}
</style>
