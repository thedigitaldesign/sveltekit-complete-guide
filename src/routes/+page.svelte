<script lang="ts">
	import ColorSlider from "../components/ColorSlider.svelte"
import Fun from "../components/Fun.svelte"

  let name = 'Rebekah'
  let fontSize = 16

  let red = 100
  let green = 100
  let blue = 100
</script>

<div>
	<h1>Fun</h1>
	<p>Fun stuff goes here</p>
</div>

<Fun />

<h2>My name is sezy {name}</h2>

<input type="text" name="name" bind:value={name} />

<br>
<br>
<br>

<input type="range" name="fontSize" bind:value={fontSize} />
<h2 style="font-size: {fontSize}px;">Font Size: {fontSize}</h2>

<div id="color-slider">
  <ColorSlider colorName="red" bind:colorValue={red} />
  <ColorSlider colorName="green" bind:colorValue={green} />
  <ColorSlider colorName="blue" bind:colorValue={blue} />

  <div class="color-swatch" style="background-color: rgb({red}, {green}, {blue});"></div>

  <p style="font-size: 30px; text-align: center;">rgb ({red}, {green}, {blue})</p>
</div>

<style lang="less">
	h1 {
		color: red;
	}

  #color-slider {
    width: 100%;
    
    input {
      width: 100%;
    }

    .color-swatch {
      border: 4px dashed black;
      width: 100%;
      height: 200px;
      margin-top: 20px;
      margin-bottom: 40px;
    }
  }
</style>
