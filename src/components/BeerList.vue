<template lang="html">
<div id="">
  <main-header title='Beer' />
  <select v-on:change='handleSelect' v-model='selectedBeer'>
    <option v-for='(beer, index) in beers' :beer='beer' :key='index'>{{beer.name}}</option>
  </select>
</div>
</template>

<script>
import { eventBus } from '../main.js';
import MainHeader from '@/components/MainHeader';


export default {
  name: 'beers-list',
  data(){
    return{
      'selectedBeer': {}
    }
  },
  props: ['beers'],
  components: {
    'main-header': MainHeader
  },
  methods: {
    handleSelect(){
      eventBus.$emit('selectedBeer', this.selectedBeer)
    }
  }
}
</script>

<style lang="css" scoped>
</style>
