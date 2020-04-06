<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Hi"/> -->
    <toDo />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import toDo from './components/toDo.vue'

export default {
  name: 'app',
  components: {
    // HelloWorld,
    toDo
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
