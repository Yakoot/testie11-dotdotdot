<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <read-more/>
  </div>
</template>

<script>
import ReadMore from './components/ReadMore.vue'

export default {
  name: 'app',
  components: {
    ReadMore
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
