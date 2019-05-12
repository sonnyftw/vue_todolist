<template>
  <header class="header">
    <h1>Todo List With VueJS</h1>
    <div id="nav">
      <router-link class="nav-item" to="/">Home</router-link> | 
      <router-link class="nav-item" to="/about">About</router-link>
    </div>
  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;
}

.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
}
</style>