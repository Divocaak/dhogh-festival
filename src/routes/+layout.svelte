<script>
	import Analytics from '$lib/Analytics.svelte';
</script>

<slot></slot>
<Analytics />

<style>
	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Regular.otf') format('opentype');
		font-weight: 400;
		font-style: normal;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Medium.otf') format('opentype');
		font-weight: 500;
		font-style: normal;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Bold.otf') format('opentype');
		font-weight: 700;
		font-style: normal;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Black.otf') format('opentype');
		font-weight: 900;
		font-style: normal;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Light.otf') format('opentype');
		font-weight: 300;
		font-style: normal;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Regular-Italic.otf') format('opentype');
		font-weight: 400;
		font-style: italic;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Medium-Italic.otf') format('opentype');
		font-weight: 500;
		font-style: italic;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Bold-Italic.otf') format('opentype');
		font-weight: 700;
		font-style: italic;
		font-display: swap;
	}

	@font-face {
		font-family: 'GT Pressura LCGV';
		src: url('/fonts/GT-Pressura-LCGV-Extended-Black-Italic.otf') format('opentype');
		font-weight: 900;
		font-style: italic;
		font-display: swap;
	}

	:global(:root) {
		--yellow: #FFCE00;
		--black: #20201D;
		--white: #ffffff;

		--card-border-radius: 1rem;

		--general-px: 5rem;
		--general-px-sm: 2rem;

		--fs-32: clamp(24px, 1.67vw, 32px);
		--fs-96: clamp(64px, 5vw, 96px);
		--fs-44: clamp(32px, 2.29vw, 44px);
		--fs-18: clamp(16px, 0.94vw, 18px);
	}

	:global(body) {
		margin: 0;
		background-color: var(--black);
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(.tt-uppercase) {
		text-transform: uppercase;
	}

	:global(.tix-button) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 500;
		font-style: normal;
		font-size: var(--fs-32);
		line-height: 130%;
		letter-spacing: -1%;
	}

	:global(.f0) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 500;
		font-style: normal;
		font-size: var(--fs-96);
		line-height: 79%;
		letter-spacing: -1%;
	}

	:global(.f1) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 700;
		font-style: normal;
		font-size: var(--fs-44);
		line-height: 95%;
		letter-spacing: -1%;
	}

	:global(.f2) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 500;
		font-style: normal;
		font-size: var(--fs-32);
		line-height: 130%;
		letter-spacing: -1%;
	}

	:global(.f3) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 400;
		font-style: normal;
		font-size: var(--fs-18);
		line-height: 140%;
		letter-spacing: 0%;
	}

	:global(.f4) {
		font-family: 'GT Pressura LCGV', sans-serif;
		font-weight: 500;
		font-style: normal;
		font-size: var(--fs-18);
		line-height: 150%;
		letter-spacing: 0%;
	}
</style>
