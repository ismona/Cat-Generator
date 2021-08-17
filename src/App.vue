<template>
  <hello-cat></hello-cat>
</template>

<script>
import HelloCat from './components/HelloCat.vue'

export default {
  name: 'App',
  components: {
    HelloCat
  }
}
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
</style>
