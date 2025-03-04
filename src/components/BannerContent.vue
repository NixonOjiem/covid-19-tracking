<template>
    <div class="banner">
      <!-- Your HTML goes here -->
       <div class="simple-introduction">
            <p>
                Welcome to my COVID-19 Tracker, your go-to source for the latest pandemic statistics. 
                Simply search for any country to get up-to-date information on active cases, new cases, total cases, 
                new deaths, total deaths, and recoveries. Stay informed with real-time data and make well-informed 
                decisions to keep yourself and your loved ones safe.
            </p>
       </div>
       <div class="simple-image">
            <img src="@/assets/Doctor and nurse pic.jpg" alt="Image of doctor and nurse" />
       </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BannerContent',
    data() {
      return {
        // Your component data goes here
        imageSrc: require('@/assets/Doctor_nurse_image.jpg')
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
  };
  </script>
  
  <style scoped>
  .banner {
    width: 100%;
    height: auto;
    position: absolute;
    z-index: -1;
    margin-top: 70px;
    display: flex;
    flex-direction: row;
  }

  .simple-introduction{
    width: 50%;
  }
  .simple-image {
  /* Set your desired dimensions */
  width: 50%;  /* or fixed width like 600px */
  height: 400px; /* adjust as needed */
  max-width: 1000px; /* optional max constraint */
  overflow: hidden; /* hide any image overflow */
  position: relative;
  background: #f0f0f0; /* fallback color while loading */
}

.simple-image img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* or 'contain' based on needs */
  display: block;
  object-position: center center; /* adjust focus area */
}
  </style>