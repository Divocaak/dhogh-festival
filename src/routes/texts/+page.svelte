<script>
	import { lang } from '$lib/LangStore.js';
	import langs from '$lib/localization.json';
</script>

<h1>festival</h1>
<div class="test">
	<p>{langs[$lang].festival[0]}</p>
	<p>{langs[$lang].festival[1]}</p>
</div>

<h1>lorem ipsum dolor sit amet</h1>
<h2>lorem ipsum dolor sit amet</h2>
<h3>lorem ipsum dolor sit amet</h3>
<p>
	Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Duis ante orci, molestie vitae vehicula
	venenatis, tincidunt ac pede. Duis bibendum, lectus ut viverra rhoncus, dolor nunc faucibus
	libero, eget facilisis enim ipsum id lacus. Nullam sit amet magna in magna gravida vehicula.
	Suspendisse sagittis ultrices augue. Etiam dictum tincidunt diam. Integer lacinia. Nullam at arcu
	a est sollicitudin euismod. Pellentesque arcu. Aliquam id dolor. Aenean id metus id velit
	ullamcorper pulvinar. Donec vitae arcu. Suspendisse nisl. Nunc auctor. Nunc tincidunt ante vitae
	massa.
</p>
<br />
<br />
<br />
<br />
<br />
<br />

<style>
	:global(body) {
		background-color: white;
	}

	h1 {
		width: 100%;
		text-align: center;
	}

	.test {
		display: flex;
		flex-direction: row;

		gap: 3rem;
		justify-content: center;
	}

	.test p {
		width: 570px;
	}

	@media (max-width: 1200px) {
		.test {
			flex-direction: column;
		}

		.test p {
			width: calc(100% - 2 * 3rem);
			padding: 0 3rem;
		}
	}
</style>
