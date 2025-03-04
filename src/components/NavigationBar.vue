<template>
    <nav class="navigation-bar">
        <ul>
            <li>Portfolio</li>
            <li>Covid 19 summary</li>
            <li>GitHub</li>
        </ul>
    </nav>
  </template>
  
  <script>
  export default {
    name: 'NavigationBar',

    data() {
      return {
      };
    },

    methods: {
    }

  };
  </script>
  
  <style scoped>
  .navigation-bar{
    background-color: #063970;
    height: 70px;
    width: 100%;
    margin: 0;
    border: 0;
    padding: 0;
  }

.navigation-bar ul{
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: space-between; /* Key property */
    width: 100%;
    height: 100%;
    align-items: center;
}

.navigation-bar li {
    /* display: inline-block; Makes list items horizontal */
    padding: 20px; /* Adjust as needed */
    color: white; /* For better visibility */
    list-style: none;
}

.navigation-bar li:first-child {
  margin-right: auto;
}

.navigation-bar li:last-child {
  margin-left: auto;
}

.navigation-bar li:nth-child(2) {
  margin: 0 auto;
}
  </style>