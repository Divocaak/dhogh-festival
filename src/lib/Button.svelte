<script>
	export let label = 'clck';
	export let href = '';
	export let target = '_blank';
	export let bgColor = 'var(--black)';
	export let txtColor = 'var(--shadow)';
    export let marginAuto = true;
</script>

<a style="--background-color: {bgColor}; --text-color: {txtColor};" class:margin-auto={marginAuto} {href} {target}>{label}</a>

<style>
	:root {
		--text-color: var(--shadow);
		--background-color: var(--black);
	}

	a {
        position: relative;
        display: block;
        width: max-content;

		text-transform: uppercase;
		background-color: var(--background-color);
		color: var(--text-color);
		padding: 1.25rem 1.75rem;

        transition: all .2s ease-in-out;
	}

    a:hover{
        color: var(--background-color);
        background-color: var(--text-color);
    }

    .margin-auto{
        margin: auto;
    }
</style>
