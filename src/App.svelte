<svelte:head>
	<link href="https://stackpath.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-Vkoo8x4CGsO3+Hhxv8T/Q5PaXtkKtu6ug5TOeNV6gBiFeWPGFN9MuhOf23Q9Ifjh" crossorigin="anonymous">
</svelte:head>

<script>
import Introduction from './Introduction.svelte'
</script>

<main>
	<div class="row">
		<div class="col-sm-0 col-md-3"></div>
		<div class="col-sm-4 col-md-6"><Introduction /></div>
		<div class="col-sm-0 col-md-3"></div>
	</div>

</main>

<style>
	:global(body){
		background: rgb(20,20,20) !important;
		color: white !important;
		padding-top: 20%;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
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