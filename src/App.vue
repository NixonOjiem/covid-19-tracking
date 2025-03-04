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
html, body {
  margin: 0;
  padding: 0;
  border: 0;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 0;
  padding: 0;
}

.container {
  margin: 0;
  padding: 0;
  border: 0;
}

</style>
