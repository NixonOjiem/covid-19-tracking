<template>
    <div class="banner">
      <img :src="imageSrc" alt="Image of doctor and nurse" />
      <p class="banner-text">
        Welcome to our COVID-19 Tracker, your go-to source for the latest 
        pandemic statistics. Simply search for any country to get up-to-date
        information on active cases, new cases, total cases, new deaths, total 
        deaths, and recoveries. Stay informed with real-time data and make well-informed 
        decisions to keep yourself and your loved ones safe.
      </p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'BannerContent',
    data() {
      return {
        imageSrc: require('@/assets/doctors-mask-superJumbo.jpg')
      };
    }
  };
  </script>
  
  <style scoped>
  .banner {
    width: 100%;
    height: 600px;
    position: relative; /* Make the banner a positioning context */
    z-index: -1;
    overflow: hidden;
  }
  
  .banner img {
    width: 100%;
    height: 100%;
    object-fit: cover; /* Ensures the image covers the div without stretching */
    display: block;
    object-position: center center; /* Centers the image */
  }
  
  .banner-text {
    position: absolute; /* Position the text absolutely within the banner */
    top: 50%; /* Center vertically */
    left: 50%; /* Center horizontally */
    transform: translate(-50%, -50%); /* Adjust for centering */
    color: white; /* Text color for better visibility */
    background-color: rgba(0, 0, 0, 0.5); /* Optional: Add a semi-transparent background for better readability */
    padding: 20px; /* Optional: Add padding for better spacing */
    text-align: center; /* Center the text */
    width: 80%; /* Optional: Adjust width as needed */
  }
  </style>