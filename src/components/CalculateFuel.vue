<template>
  <div class="font-sans px-4 max-w-sm mx-auto">
    <div class="my-8">
      <h1 class="text-center">Gasolina VS Etanol</h1>
    </div>

    <form @submit.prevent="calculateFuel">
      <div class="flex -mx-4">
        <div class="flex-1 mx-4">
          <label class="tracking-wide text-xs font-bold block mb-1 uppercase" for="ethanol">Preço do Etanol</label>
          <div class="flex">
            <div class="bg-grey-light p-3 rounded rounded-r-none font-bold text-grey-darker tracking-wide">R$</div>
            <div class="flex-1">
              <input class="rounded rounded-l-none	border w-full p-3" name="ethanol" v-model="ethanol" id="ethanol" type="text">
            </div>
          </div>
        </div>
        <div class="flex-1 mx-4">
          <label class="tracking-wide text-xs font-bold block mb-1 uppercase" for="gasoline">Preço da Gasolina</label>
          <div class="flex">
            <div class="bg-grey-light p-3 rounded rounded-r-none font-bold text-grey-darker tracking-wide">R$</div>
            <div class="flex-1">
              <input class="rounded rounded-l-none border w-full p-3" name="gasoline" v-model="gasoline" id="gasoline" type="text">
            </div>
          </div>
        </div>
      </div>
      <div class="mt-3">
        <button type="submit" class="w-full p-3 text-center bg-pink rounded text-white uppercase font-bold">calcular</button>
      </div>
    </form>

    <div class="bg-green py-8 mt-4 rounded shadow border-green-dark" v-if="finalFuel">
      <p class="text-center"><small class="text-white uppercase tracking-wide">Abasteça com</small></p>
      <p class="text-center text-xl font-bold text-green-darker uppercase mt-2">{{ finalFuel }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CalculateFuel',
  props: {
    // msg: String
  },
  data() {
    return {
      finalFuel : null,
      gasoline : null,
      ethanol : null,
    }
  },
  methods: {
    calculateFuel() {
      if((this.ethanol / this.gasoline) >= 0.7) return this.finalFuel = 'Gasolina';
      return this.finalFuel = 'Etanol';
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
