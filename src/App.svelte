<script>
	import List from './List.svelte';
	import Sidebar from './Sidebar.svelte';

</script>

<main>
	<h1>Svelte ToDo!</h1>
	<Sidebar/>
  <List/>
</main>

<style>

	main {
		text-align: center;
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
		background-color: darkgray;

	}
	h1 {
		color: black;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}
	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>