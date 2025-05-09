<script>
	import { onDestroy } from 'svelte';

	export let backgroundColor = 'var(--black)';
	export let heading;
	export let headingSvg = 0;
	export let headingClr = 'var(--shadow)';
	export let headingBgClr = 'var(--black)';
	export let topSvg = 0;

	const svgs = [
		{
			w: 379,
			h: 145,
			d: 'M347.706 0L305.286 0V8.55337L201.67 8.55337V36.25H166.204V8.55337L131.085 8.55337V19.1433L75.1045 19.1433V0L-6.10352e-05 0L-6.10352e-05 87.5702H16.3421L16.3421 108.75L96.6623 108.75V134.003L192.629 134.003V119.34H263.214V145H305.286V119.34H379V53.3567L347.706 53.3567V0Z'
		},
		{
			w: 462,
			h: 132,
			d: 'M38.1468 132L89.8569 132L89.8569 124.213L216.165 124.213L216.165 99L259.398 99L259.398 124.213L302.207 124.213L302.207 114.573L370.448 114.573L370.448 132L462 132L462 52.2809L442.079 52.2809L442.079 33L344.169 33L344.169 10.0113L227.185 10.0113L227.185 23.3596L141.143 23.3596L141.143 1.77262e-05L89.8569 1.32426e-05L89.8569 23.3596L9.49765e-06 23.3595L4.24639e-06 83.4269L38.1468 83.4269L38.1468 132Z'
		}
	];

	const topSvgs = [
		{
			w: 1512,
			h: 207,
			d: 'M1409.11 89.0337L1512 89.0337V206.5L0 206.5L3.07728e-05 97.5483H50.2012L50.2012 52.0311L161.538 52.0311V68.5373L210.249 68.5373V48.0182L269.396 48.0182V28.5109L411.053 28.5109V0.00012207L524.379 0.00012207V28.0107L673.491 28.0107V52.5199H725.183V22.0084L830.059 22.0084V35.0133L883.74 35.0133V57.5218L987.124 57.5218V18.5071L1164.07 18.5071V39.515L1200.36 39.515V57.5218L1280.38 57.5218V35.0133L1409.11 35.0133V89.0337Z'
		},
		{
			w: 1512,
			h: 201,
			d: 'M1410 29.2879L1512 29.2879V200.5L0 200.5L3.07728e-05 70.2456H50.2012L50.2012 89.894L93.5 89.894L93.5 32.8232L164.5 32.8232V70.2456L226 70.2456V53.5303L298 53.5303V69.1869H357.5V53.5303L558.5 53.5303V100.5H603.5V64.1364L692 64.1364H710.5V21.7121L874 21.7121V64.1364H923.5V44.4394L1016.5 44.4394V87.8738H1074.5V55.0455H1107.5V30.5L1208 30.5V44.4394V55.0455V77.7728L1284 77.7728V0.5L1410 0.5V29.2879Z'
		},
		{
			w: 1512,
			h: 201,
			d: 'M0 200.5L3.07728e-05 36.957L133 36.957V59.8516L266 59.8516V100.251L385 100.251V43.3928H431V59.8516L536.5 59.8516V36.4102L667.5 36.4102V59.8516H703.5V85.2881L805 85.2881V10.4751L917 10.4751V36.4102L1006 36.4102V59.8516L1175 59.8516V36.4102L1242.5 36.4102V61.3479L1306.5 61.3479V10.4751L1387 10.4751V36.957L1458 36.957V0.5L1512 0.5V200.5L0 200.5Z'
		},
		{
			w: 1512,
			h: 200,
			d: 'M1512 200L0 200L0 55.4273L87.5 55.4273V22.1709L245 22.1709V92.8407L307.5 92.8407V39.7229L361 39.7229V0L407.5 0V66.9746H476.5V22.1709L576.5 22.1709V55.4273L650.5 55.4273V33L727 33V55.4273H761V113H864.5V92.8407L908 92.8407V27.4376L1001.5 27.4376V8.5L1113 8.5V66.9746L1250.5 66.9746V8.5L1388 8.5V92.8407L1501.5 92.8407H1512V200Z'
		}
	];

	let headingSvgCounter = headingSvg;
	/* const headingSvgInterval = setInterval(() => {
		headingSvgCounter = (headingSvgCounter + 1) % svgs.length;
	}, 1000); */

	let topSvgCounter = topSvg;
	const topSvgInterval = setInterval(() => {
		topSvgCounter = (topSvgCounter + 1) % topSvgs.length;
	}, 1000);

	onDestroy(() => {
		/* clearInterval(headingSvgInterval); */
		clearInterval(topSvgInterval);
	});
</script>

<div
	class="wrapper"
	style="--bg-color: {backgroundColor}; --heading-color: {headingClr}; --heading-bg-color: {headingBgClr};"
>
	<svg
		width={topSvgs[topSvgCounter].w}
		height={topSvgs[topSvgCounter].h}
		viewBox="0 0 {topSvgs[topSvgCounter].w} {topSvgs[topSvgCounter].h}"
		class="top-svg"
		xmlns="http://www.w3.org/2000/svg"
	>
		<path d={topSvgs[topSvgCounter].d} />
	</svg>

	<div class="heading-wrapper">
		<h1>{heading}</h1>
		<svg
			width={svgs[headingSvgCounter].w}
			height={svgs[headingSvgCounter].h}
			viewBox="0 0 {svgs[headingSvgCounter].w} {svgs[headingSvgCounter].h}"
			xmlns="http://www.w3.org/2000/svg"
		>
			<path d={svgs[headingSvgCounter].d} />
		</svg>
	</div>

	<slot></slot>
</div>

<style>
	:root {
		--bg-color: var(--black);
		--heading-color: var(--shadow);
		--heading-bg-color: var(--black);
	}

	.wrapper {
		position: relative;
		background-color: var(--bg-color);
		min-height: 100vh;
	}

	.heading-wrapper {
		position: relative;
		width: 100%;
		height: 10rem;
	}

	.heading-wrapper h1,
	.heading-wrapper svg {
		position: absolute;

		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		margin: 0;
	}

	.heading-wrapper svg {
		width: 100%;
		fill: var(--heading-bg-color);
	}

	h1 {
		color: var(--heading-color);
		z-index: 1;
	}

	.top-svg {
		position: absolute;
		top: -150px;
		width: 100%;
		fill: var(--bg-color);
	}

	@media (max-width: 1200px) {
		.top-svg {
			top: -120px;
		}
	}
</style>
