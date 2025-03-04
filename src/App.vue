<template>
  <div class="container">
    <NavigationBar />
    <BannerContent />
  </div>
</template>

<script>
import BannerContent from './components/BannerContent.vue'
import NavigationBar from './components/NavigationBar.vue'

export default {
  name: 'App',
  data() {
      return {
        // Your component data goes here
      };
    },
    methods: {
      // Your component methods go here
    },
    computed: {
      // Your computed properties go here
    },
    components: {
      // Your child components go here
    },
    mounted() {
      // Code to run when the component is mounted
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
