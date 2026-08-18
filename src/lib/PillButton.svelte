<script>
	import Pill from './Pill.svelte';
	export let label;
</script>

<a href="https://goout.net/cs/dhogh-festival/szepoly/" target="_blank">
	<Pill tix={true} {label} hoverfx={true}/>
</a>