<script lang="ts">
	let colorList: string[] = ['red', 'green', 'blue', 'purple']
	let newColor: string = ''

	const addColor = () => {
		if (!newColor) return
    
		colorList = [...colorList, newColor]
		newColor = ''
	}
</script>

<select name="colorListSelect">
	{#each colorList as color}
		<option value={color}>{color}</option>
	{/each}
</select>

<input type="text" name="colorListAdd" bind:value={newColor} />
<button on:click={addColor}>Add Color</button>
