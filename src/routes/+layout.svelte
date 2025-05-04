<slot></slot>

<style>
	@font-face {
		font-family: 'InterItalic';
		src: url('fonts/Inter/Inter-Italic-VariableFont_opsz,wght.ttf');
		font-weight: 100 1000;
		font-style: italic;
	}

	@font-face {
		font-family: 'Inter';
		src: url('fonts/Inter/Inter-VariableFont_opsz,wght.ttf');
		font-weight: 100 1000;
		font-style: normal;
	}

	@font-face {
		font-family: 'PPSupplyMono';
		src: url('fonts/PPSupplyMono-Variable.ttf');
		font-weight: 100 1000;
		font-style: normal;
	}

	:global(:root) {
		--black: #000000;
		--shadow: #dadada;
		--red: #e73c30;
		--blue: #7f9ac2;
		--green: #52774f;
		--peach: #f9c4aa;
		--violet: #8e79b6;

		--general-px: 5rem;

		/* vw = px value / 19.2 */
		/* rem = px value / 16 */
		--fs-12: clamp(12px, 0.625vw, 1rem);
		--fs-14: clamp(14px, 0.73vw, 1.25rem);
		--fs-16: clamp(16px, 0.83vw, 1.5rem);
		--fs-18: clamp(18px, 0.94vw, 1.75rem);
		--fs-20: clamp(20px, 1.04vw, 2rem);
		--fs-24: clamp(24px, 1.25vw, 2.5rem);
		--fs-32: clamp(32px, 1.67vw, 3rem);
		--fs-48: clamp(48px, 2.5vw, 3rem);
		--fs-64: clamp(64px, 3.33vw, 4rem);
		--fs-72: clamp(72px, 3.75vw, 4.5rem);
		--fs-150: clamp(150px, 9.81vw, 9.37rem);
	}

	:global(h1, h2, h3, h4, h5, h6, p, a, button) {
		font-family: 'PPSupplyMono', monospace;
		font-style: normal;

		letter-spacing: -0.02em;
		word-spacing: -0.3em;

		color: var(--black);
	}

	:global(p) {
		line-height: 1.5em;
		font-weight: 300;
	}

	:global(h1, h2, h3, h4, h5, h6) {
		text-transform: uppercase;
		font-weight: 400;
	}

	:global(a) {
		text-decoration: none;
		transition: all var(--link-transition);
	}

	:global(a:hover) {
		color: var(--pink);
	}

	:global(body) {
		margin: 0;
        background-color: var(--black);
	}
</style>
