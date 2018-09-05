<template>
  <div id="app">
    <calculate-fuel></calculate-fuel>
    <next-features></next-features>
  </div>
</template>

<script>
import CalculateFuel from './components/CalculateFuel.vue'
import NextFeatures from './components/NextFeatures.vue'

export default {
  name: 'app',
  components: {
    CalculateFuel,
    NextFeatures
  }
}
</script>

<style>
@import url('https://cdn.jsdelivr.net/npm/tailwindcss/dist/tailwind.min.css');
</style>
