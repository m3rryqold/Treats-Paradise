<template>
  <div>
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <navbar/>
    <Cakes/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import navbar from './components/navbar'
import Cakes from './components/Cakes'

export default {
  name: 'App',
  components: {
    Cakes,navbar
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
