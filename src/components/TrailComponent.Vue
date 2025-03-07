<template>
    <div class="example-component">
      <h1>{{ title }}</h1>
      <p>{{ message }}</p>
    </div>
  </template>
  
  <script>
  export default {
    name: 'TrailComponent',
    data() {
      return {
        title: 'Hello, Vue!',
        message: 'This is a basic Vue component structure.'
      };
    }
  };
  </script>
  
  <style scoped>
  .example-component {
    text-align: center;
    color: #42b983;
  }
  </style>