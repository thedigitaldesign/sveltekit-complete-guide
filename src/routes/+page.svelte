<script lang="ts">
	import FormContainer from '../components/FormContainer.svelte'

  const onFormSubmit = (event: CustomEvent) => {
    console.log(event.detail)

    const { name, number } = event.detail

    console.log(name, number, 'from +page.svelte')
  }
</script>

<div>
	<FormContainer on:form_submit={onFormSubmit} />
</div>
