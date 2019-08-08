<template lang="html">
<div id="app">
  <nav>
    <router-link to='/beers'>Beers</router-link>
    <router-link to='/favourites'>Favourites</router-link>
  </nav>
  <router-view id="view" /> <!-- confirm what this does -->
</div>
</template>

<script>
export default {
}
</script>

<style lang="css" scoped>
</style>
