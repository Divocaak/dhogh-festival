<script>
	import Button from './Button.svelte';

	export let label;
	export let desc;
	export let descLong;
	export let imgPath;
	export let price;
	export let link;
</script>

<div class="wrapper">
	<div class="img"></div>
	<div class="texts">
		<h1>{label}</h1>
		<h2>({desc})</h2>
		<p>{descLong}</p>
		<div class="cta-wrapper">
			<p>{price},-</p>
			<Button label="koupit" href={link} marginAuto={false}/>
		</div>
	</div>
</div>

<style>
	h1,
	h2,
	p {
		color: var(--shadow);
        margin: .5rem 0;
	}

	.wrapper {
		flex: 1;
		display: flex;
		flex-direction: row;
	}

	.img {
		flex: 1;
		/* aspect-ratio: 1 / 1; */
		background-image: url('tst.jpg');
		background-size: cover;
		background-position: center;
	}

	.texts {
		flex: 1;
		display: flex;
        flex-direction: column;
        justify-content: center;
        padding-left: 1rem;
	}

    .cta-wrapper{
        display: flex;
        flex-direction: row;
        width:100%;
        align-items: center;
        justify-content: space-between;
    }
</style>
