<script lang="ts">
	import ColorSlider from '../components/ColorSlider.svelte'
	import Fun from '../components/Fun.svelte'

	let name = 'Rebekah'
	let fontSize = 16

	let red = 100
	let green = 100
	let blue = 100

	let vert = 50
	let horz = 50

	const doClickStuff = (e) => {
		console.log('You clicked the button!', e)
	}

	const doSlideStuff = (e) => {
		console.log('You slid the slider!', e.target.value)
	}

	const doInputSlideStuff = (e) => {
		console.log('You input slid the slider!', e)
	}

	const keyup = (e) => {
		console.log('You pressed a key!', e.key)

		if (e.key === 'ArrowUp') vert -= 1
		else if (e.key === 'ArrowDown') vert += 1
		else if (e.key === 'ArrowLeft') horz -= 1
		else if (e.key === 'ArrowRight') horz += 1

    console.log(vert, horz)
	}

	const submitForm = (e) => {
		console.log('You submitted the form!', e)
	}
</script>

<div>
	<h1>Fun</h1>
	<p>Fun stuff goes here</p>
</div>

<Fun />

<h2>My name is sezy {name}</h2>

<input type="text" name="name" bind:value={name} />

<br />
<br />
<br />

<input type="range" name="fontSize" bind:value={fontSize} />
<h2 style="font-size: {fontSize}px;">Font Size: {fontSize}</h2>

<div id="color-slider">
	<ColorSlider colorName="red" bind:colorValue={red} />
	<ColorSlider colorName="green" bind:colorValue={green} />
	<ColorSlider colorName="blue" bind:colorValue={blue} />

	<div class="color-swatch" style="background-color: rgb({red}, {green}, {blue});" />

	<p style="font-size: 30px; text-align: center;">rgb ({red}, {green}, {blue})</p>
</div>

<div style="margin-top: 20px;">
	<button type="button" on:click|once={doClickStuff}>Hey I'm a button</button>
	<input type="range" on:input={doInputSlideStuff} on:change={doSlideStuff} />
</div>

<form on:submit|preventDefault={submitForm}>
	<button type="submit">Submit</button>
</form>

<svelte:window on:keydown={keyup} />

<div class="container-window">
	<div class="box" style="top: {vert}%; left: {horz}%;" />
</div>

<style lang="less">
	h1 {
		color: red;
	}

	#color-slider {
		width: 100%;

		.color-swatch {
			border: 4px dashed black;
			width: 100%;
			height: 200px;
			margin-top: 20px;
			margin-bottom: 40px;
		}
	}

	.container-window {
		background-color: #999;
		position: relative;
		width: 100%;
		height: 400px;
    overflow: hidden;

		.box {
			position: absolute;
			width: 100px;
			height: 100px;
			background-color: #333;
			border: 2px solid #000;
			border-radius: 5px;
			top: 50%;
			left: 50%;
			transform: translate(-50%, -50%);
		}
	}
</style>
