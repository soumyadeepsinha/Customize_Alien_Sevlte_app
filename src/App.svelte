<script>
	let hue = 0;
	let brightness = 100;
	let saturation = 100;
	let hatSizes = 1;

	$: aliencolor = `
	filter: hue-rotate(${hue}deg)
	brightness(${brightness}%)
	saturate(${saturation}%);`;

	$: hatStyle = `transform: translate(-55%, -35%) scale(${hatSizes})`;
</script>
<main>
	<h1>Your Alien Agent</h1>
	<div class="alien">
		<img style="{aliencolor}" class="alien-body" src="./assets/alien.png" alt="Alien">
		<img style="{hatStyle}" class="hat" src="./assets/hat-2.png" alt="Hat">
	</div>
	<br>
	<label for="hue">Color</label>
	<input type="range" min="0" max="360" bind:value={hue}/> <br />
	<label for="brightness">Brightness</label>
	<input type="range" min="50" max="150" bind:value={brightness}/> <br />
	<label for="saturation">Saturation</label>
	<input type="range" min="0" max="250" bind:value={saturation}/> <br />
	<label for="hatsize">Hat Size</label>
	<input type="range" step="0.05" min="0.3" max="1.5" bind:value={hatSizes}/>
</main>

<style>

	main {
		width: 100%;
		display: flex;
		align-items: center;
		flex-direction: column;
		overflow-x: hidden;
	}

	.alien {
		margin-top: 50px;
		position: relative;
		width: 300px;
	}

	.alien-body {
		width: 100%;
		height: auto;
	}

	.hat {
		position: absolute;
		top: 0;
		left: 50%;
		transform: translate(-55%, -35%);
	}

	img{
		image-rendering: crisp-edges;
	}

	</style>