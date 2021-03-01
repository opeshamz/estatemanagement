<template>
  <div id="app">
    <Navbar/>

    <Banner/>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Banner from './components/Banner.vue'

export default {
  name: 'app',
  components: {
 Navbar,
 Banner
 }
}
</script>

<style scope >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  
 
 
}






</style>
