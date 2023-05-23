<script lang="ts">
  let name = 'world';
  $: greeting = `Hello ${name.toUpperCase()}!`;

  let number = 55
  $: dogYears = number * 7

  const color = (red: number, green: number, blue: number) => {
    return `rgb(${red}, ${green}, ${blue})`
  }

  let red = 255
  let green = 0
  let blue = 127

  $: colorValue = color(red, green, blue)

  setTimeout(() => {
    red = 0
    green = 255
    blue = 255
  }, 1500);

  $: console.log('colorValue', colorValue)
  $: {
    console.log('red: ', red)
    console.log('green: ', green)
    console.log('blue: ', blue)
  }
</script>

<div>
  <label for="name">Name</label>
  <input type="text" name="name" bind:value={name} />
  <h2>Name: {name}</h2>
  <h3>{greeting}</h3>

  <label for="number">Number</label>
  <input type="text" name="number" bind:value={number} />
  <h2>Number: {number}</h2>
  <h2>Dog Years: {dogYears}</h2>

  <h2 style="color: {colorValue}">{name} with a side of {number}</h2>
</div>
