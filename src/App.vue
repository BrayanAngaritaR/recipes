<template>
   <img alt="BePro Digital Logo" src="https://bepro.digital/frontend/assets/img/bepro-logo.png" width="80" />

   <div id="nav">
      <router-link to="/">Inicio</router-link>
   </div>
   <router-view></router-view>
</template>

<script>
   export default {
      name: "App"
   };
</script>

<style>
   #app {
      font-family: Avenir, Helvetica, Arial, sans-serif;
      -webkit-font-smoothing: antialiased;
      -moz-osx-font-smoothing: grayscale;
      text-align: center;
      color: #2c3e50;
      margin-top: 60px;
   }

   .category_container {
      border: 1px solid rgb(255, 240, 31);
      padding: 50px;
   }

   .search-input {
      border: none;
      border-bottom: 1px solid rgb(255, 240, 31);
      min-height: 20px;
      margin-top: 20px;
      margin-bottom: 20px;
   }

   * {
      font-family: monospace;
   }
</style>
