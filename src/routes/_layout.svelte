<script>
	import Nav from '../components/Nav.svelte';

	export let segment;
</script>

<style>
	main {
		background-color: #004c6d;
		margin: 0 auto;
		box-sizing: border-box;
		padding-bottom: 2rem;
		height: 100%;
	}
</style>

<Nav {segment}/>

<main>
	<slot></slot>
</main>