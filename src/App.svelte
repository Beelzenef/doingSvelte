<script>
	export let name;
	import Credits from './cmps/Credits.svelte';

	let pulsaPrimeraVez = "Pulsa por primera vez";
	let pulsaOtraVez = "Pulsa otra vez";
	let pulsaciones = 0;

	function showAlert() {
		alert("surprise!");
	}

	function pulsarBoton() {
		pulsaciones++;
	}
</script>

<main>
	<h1>Hello {name}!</h1>
	<p>Visit the <a href="https://svelte.dev/tutorial">Svelte tutorial</a> to learn how to build Svelte apps.</p>
	<button on:click={showAlert}>
		press me!
	</button>
	<p>Operador ternario dentro de contenido de elementos</p>
	<button on:click={pulsarBoton}>
		{ pulsaciones === 0 ? pulsaPrimeraVez : pulsaOtraVez }
	</button>
	<p>Llamando a métodos con operador ternario</p>
	<button on:click={pulsarBoton}>
		{ pulsaciones === 4 ? showAlert() : "awesome" }
	</button>
	<Credits/>
</main>

<style>
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