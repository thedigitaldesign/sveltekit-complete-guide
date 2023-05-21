<script lang="ts">
	import { createEventDispatcher } from 'svelte'

  const dispatch = createEventDispatcher()

	let name = 'Josh'
	let number = 68

	const onSubmit = (event: Event) => {
		console.log(`Hello ${name}! Your favorite number is ${number}.`)

    dispatch('form_submit', {
      name,
      number
    })
	}
</script>

<form on:submit|preventDefault={onSubmit}>
	<label for="name">Name</label>
	<input type="text" name="name" bind:value={name} />

	<label for="favoriteNumber">Favorite Number</label>
	<input type="number" name="favoriteNumber" bind:value={number} />

	<button type="submit">Submit</button>
</form>

<style lang="less">
</style>
