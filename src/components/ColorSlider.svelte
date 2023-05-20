<script type="ts">
  export let colorName = 'red'
  export let colorValue = 100
</script>

<label for="{colorName}Slider">{colorName} ({colorValue})</label>
<input type="range" name="{colorName}Slider" bind:value={colorValue} min="0" max="255" />

<style>
  label {
    display: block;
    font-size: 20px;
    font-weight: normal;
    text-transform: capitalize;
  }

  input {
    width: 100%;
  }
</style>
