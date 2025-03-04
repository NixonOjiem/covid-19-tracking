<template>

    <div class="DynamicComponent">
      
        <div class="search-container">
            <input 
                type="search" 
                placeholder="Search for any country" 
                id="search-box" 
                v-model.trim="country" 
                class="text-input" 
                v-on:keyup.enter="handleSearch"
            />
            <button class="search-button" @click="handleSearch">Search</button>
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
      handleSearch(){
        console.log(this.country)
      },
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

  .search-container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
  }

  .text-input {
    padding: 10px;
    width: 300px;
    border: 2px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
    transition: border-color 0.3s;
  }

  .text-input:focus {
    border-color: #007BFF;
    outline: none;
  }

  .search-button {
    padding: 10px 20px;
    margin-left: 10px;
    border: none;
    border-radius: 5px;
    background-color: #007BFF;
    color: white;
    font-size: 16px;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .search-button:hover {
    background-color: #0056b3;
  }
  </style>
 
  