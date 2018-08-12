<template>
  <div id="app">
    <calculate-fuel></calculate-fuel>
  </div>
</template>

<script>
import CalculateFuel from './components/CalculateFuel.vue'

export default {
  name: 'app',
  components: {
    CalculateFuel
  }
}
</script>

<style>
@import url('https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css');
</style>
