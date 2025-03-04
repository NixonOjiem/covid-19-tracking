<template>

    <div class="DynamicComponent">
      
        <div class="search-container">
            <input type="search" placeholder="search for any country" id="searcg-box" v-model.trim="country" class="text-input"/>
            <button>Search</button>
        </div>
        

    </div>
       
    
  </template>
  
  <script>
  export default {
    name: 'DynamicComponent',
    data() {
      return {
        // Your component data goes here
        country: "",
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
  .DynamicComponent {
    background-color: #fefbf3;
    width: 100%;
    height: auto;
  }

  .search-container{
   text-align: center;
   margin-top: 10px;
  }

  .text-input{
    padding: 5px;
    width: 300px;
    text-align: center;
  }
  </style>
 
  