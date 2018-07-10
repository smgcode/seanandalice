<template>
  <div id="app">
    <Home/>
  </div>
</template>

<script>
import Home from './views/Home.vue'

export default {
  name: 'App',
  components: {
    Home,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Abril+Fatface|Roboto+Slab:300,400,700');

#app {
  font-family: 'Roboto Slab', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  overflow-wrap: break-word;
  word-wrap: break-word;
}

body {
  margin: 0;
  padding: 0;
}
</style>
