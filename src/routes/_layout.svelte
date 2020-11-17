<script>
	import Nav from '../components/Nav.svelte';
	export let segment;
</script>

<Nav/>

<main>
	<slot></slot>
</main>


<style>
	main {
		margin: 0 auto;
		color: #fff;
		font-size: 1.3vw;
	}

</style>