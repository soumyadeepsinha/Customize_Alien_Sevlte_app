<script>
	let hue = 0;
	let brightness = 100;

	$: aliencolor = `
	filter: hue-rotate(${hue}deg) brightness(${brightness}%);`;
</script>

<main>
	<img style="{aliencolor}" src="./assets/alien.png" alt="Alien">
	<input type="range" min="0" max="360" bind:value={hue}/>
	<input type="range" min="50" max="150" bind:value={brightness}/>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}
	</style>