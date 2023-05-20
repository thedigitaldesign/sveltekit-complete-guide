<script type="ts">
	import Fun from '../components/Fun.svelte'

	let name = 'hallo Rebekah'
	let favoriteColor = 'pink'
  let favoriteNumber = 68

	setTimeout(() => {
		favoriteColor = 'blue'
    favoriteNumber++
	}, 1000)
</script>

<Fun />

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<p style="color: {favoriteColor}">{name}</p>
<p>Her favorite number is: {favoriteNumber}</p>