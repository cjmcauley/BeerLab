<template lang="html">
  <div id="app">
    <nav>
      <router-link to='/beers'>Beers</router-link>
      <router-link to='/favourites'>Favourites</router-link>
    </nav>
    <router-view id="view" :beers='beers' /> <!-- confirm what this does -->
  </div>
</template>

<script>
import BeersList from './views/Beers.vue';

export default {
  name: 'app',
  data(){
    return {
      beers: []
    };
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beersFetch => this.beers = beersFetch)
  },
  components: {
    'beers-list': BeersList
  }
}
</script>

<style lang="css" scoped>
</style>
