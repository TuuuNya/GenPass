<template>
  <div id="app">
    <img src="./assets/logo.png">
              <gen-pass></gen-pass>
  </div>
</template>

<script>
import GenPass from './components/GenPass'

export default {
  name: 'app',
  components: {
    GenPass
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
