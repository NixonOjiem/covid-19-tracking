<template>
  <div class="container">
    <NavigationBar />

  </div>
</template>

<script>
import NavigationBar from './components/NavigationBar.vue'

export default {
  name: 'App',

  data(){
    return {

    }
  },

  components: {
    NavigationBar
  }

}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}
</style>
