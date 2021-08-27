<template>
  <div class="travel-information">
    <p>{{ travel.name }}といえば...</p>
    <ul>
      <li v-for="(spot, index) in travel.spots" :key="index">{{ spot }}とか</li>
    </ul>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    travel: {
      type: Object,
      required: true,
    },
  },
})
</script>
