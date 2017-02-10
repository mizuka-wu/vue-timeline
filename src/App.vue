<template>
  <div id="app">
    <img src="./assets/logo.png">
    <timeLine></timeLine>
  </div>
</template>

<script>
import 'bootstrap/dist/css/bootstrap.min.css'
import timeLine from './components/timeLine.vue'

export default {
  name: 'app',
  components: {
    timeLine
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
