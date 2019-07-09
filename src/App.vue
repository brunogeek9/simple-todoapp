<template>
  <div id="app">
    <todos></todos>
    
  </div>
  
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Todos from './components/Todos.vue'
export default {
  name: 'app',
  components: {
    // HelloWorld,
    Todos,
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
.logo{
  width: 5%;
  height: 5%;
}
li{
  list-style: none;
}
</style>
