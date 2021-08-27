<template>
  <div class="roulette">
    <h1>国内旅行先ルーレット</h1>
    <button @click="spinRoulette">旅行先は？</button>
    <h2 v-if="showTravel">{{ selectedTravel.name }}だ！</h2>
    <travel-information v-if="showTravel" :travel="selectedTravel" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import travels from '../assets/json/travels.json'

export default Vue.extend({
  data() {
    const showTravel: boolean = false
    const selectedTravel: any = {}

    return {
      showTravel,
      selectedTravel,
    }
  },
  methods: {
    spinRoulette() {
      const randomIndex = Math.floor(Math.random() * travels.length)
      this.selectedTravel = travels[randomIndex]
      this.showTravel = true
    },
  },
})
</script>

<style>
.roulette {
  width: 400px;
  margin: 0 auto;
}
</style>
