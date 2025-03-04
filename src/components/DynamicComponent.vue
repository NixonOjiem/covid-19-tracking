<template>

    <div class="DynamicComponent">
      
        <div class="search-container">
            <input 
            type="search" 
            placeholder="Search for any country..." 
            id="search-box" 
            v-model.trim="country" 
            class="modern-input" 
            v-on:keyup.enter="handleSearch"
            />
            <button class="modern-button" @click="handleSearch">Search</button>
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
  margin: 2rem 0;
  padding: 0 1rem;
  display: flex;
  flex-direction: row;
}

.search-group {
  max-width: 600px;
  margin: 0 auto;
  display: flex;
  gap: 8px;
  background: white;
  border-radius: 50px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
  transition: all 0.3s ease;
}

.search-group:focus-within {
  box-shadow: 0 6px 25px rgba(0, 0, 0, 0.15);
  transform: translateY(-2px);
}

.modern-input {
  flex: 1;
  padding: 1rem 1.5rem;
  border: none;
  border-radius: 50px;
  font-size: 1.1rem;
  background: transparent;
  outline: none;
}

.modern-input::placeholder {
  color: #999;
  font-weight: 300;
}

.modern-button {
  padding: 1rem 2rem;
  border: none;
  border-radius: 50px;
  background: #007bff;
  color: white;
  font-size: 1rem;
  font-weight: 600;
  cursor: pointer;
  transition: all 0.2s ease;
  display: flex;
  align-items: center;
  gap: 8px;
}

.modern-button:hover {
  background: #0056b3;
  transform: translateY(-1px);
  box-shadow: 0 3px 15px rgba(0, 123, 255, 0.3);
}

.modern-button:active {
  transform: translateY(0);
}

/* Optional: Add media query for mobile */
@media (max-width: 480px) {
  .search-group {
    flex-direction: column;
    border-radius: 20px;
    padding: 8px;
  }
  
  .modern-input {
    padding: 1rem;
    border-radius: 15px;
  }
  
  .modern-button {
    width: 100%;
    justify-content: center;
    border-radius: 15px;
  }
  }
  </style>
 
  