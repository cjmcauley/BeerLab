<template lang="html">
  <div>
    <beers-list :beers="beers"></beers-list>
  </div>
</template>

<script>
import { eventBus } from '../main.js';
import BeersList from '../components/BeerList.vue';

export default {
  props: ['beers'],
  data(){
    return {
      selectedBeer: null
    }
  },
  components: {
    'beers-list': BeersList
  },
  mounted(){
  eventBus.$on('selectedBeer', (beer) => {
    this.selectedBeer = beer
  })
}
}
</script>

<style lang="css" scoped>
</style>
