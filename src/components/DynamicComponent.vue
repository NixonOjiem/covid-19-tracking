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
  
      <div>
        <div v-if="isLoading">Loading COVID data...</div>
        <div v-if="errorMessage" class="error">{{ errorMessage }}</div>
        
        <div v-if="covidStats" class="stats">
          <h2>{{ country.toUpperCase() }} COVID-19 Statistics</h2>
          <div v-for="(value, key) in covidStats" :key="key" class="results">
            <strong>{{ formatKey(key) }}:</strong> {{ value }}
          </div>
        </div>
      </div>  
    </div>
  </template>
  
  <script>
  import axios from 'axios';
  
  export default {
    name: 'DynamicComponent',

    data() {
      return {
        covidStats: null,
        isLoading: false,
        errorMessage: '',
        country: '',
        // Add a cache object to store results
        cache: {}
      };
    },
    
    methods: {
      handleSearch() {
        if (this.country) {
          this.fetchData();
        }
      },
  
      async fetchData() {
        this.isLoading = true;
        this.errorMessage = '';
  
        // Check if the data for the country is already in the cache
        if (this.cache[this.country.toLowerCase()]) {
          this.covidStats = this.cache[this.country.toLowerCase()];
          this.isLoading = false;
          return;
        }
  
        const options = {
          method: 'GET',
          url: `https://covid-19-tracking.p.rapidapi.com/v1/${this.country.toLowerCase()}`,
          headers: {
            'x-rapidapi-key': 'f7171ed0damsh435a225b94967c1p1e2eb6jsn57f2abe28f90',
            'x-rapidapi-host': 'covid-19-tracking.p.rapidapi.com'
          }
        };
  
        try {
          const response = await axios.request(options);
          this.covidStats = response.data;
          // Store the result in the cache
          this.cache[this.country.toLowerCase()] = response.data;
        } catch (error) {
          this.errorMessage = `Failed to fetch COVID data for ${this.country}: ${error.response?.data?.message || error.message}`;
          console.error(error);
        } finally {
          this.isLoading = false;
        }
      },
      formatKey(key) {
        return key.replace(/_/g, ' ').toUpperCase();
      }
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
    justify-content: center;
  }
  
  .modern-input {
    padding: 1rem 1.5rem;
    border: none;
    font-size: 1.1rem;
    border-bottom: 1px solid #000;
    outline: none;
    width: 400px;
    text-align: center;
  }
  
  .modern-input::placeholder {
    color: #999;
    font-weight: 300;
  }
  
  .modern-input:focus {
    border-bottom: 2px solid #007bff;
    transition-timing-function: ease-in-out;
    transition-duration: 0.7s;
    transition: ease-in-out;
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

  .stats{
    width: 100%;
    justify-content: space-between;

  }
  </style>