<template>
  <div class="about">
    <h1>About</h1>
    <p>A simple TodoList App with VueJS employing rudimentary in-application routing and the JSON Placeholder API.</p>
    <router-link to="/"><button class="btn2">Go Back</button></router-link>
  </div>
</template>

<script>
export default {
  
}
</script>

<style scoped>
.btn2 {
  align-content: center;
  color: #ddd;
  background-color: red;
  width: 70px;
  height: 30px;
  border-radius: 10px;
  shadow: none;
  font-family:Arial, Helvetica, sans-serif;
  font-size: medium;
  font: bold;
}  
</style>