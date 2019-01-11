<template>
  <div id="app">
    <treeDrag/>
  </div>
</template>

<script>
import treeDrag from './components/treeDrag'

export default {
  name: 'App',
  components: {
    treeDrag
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
