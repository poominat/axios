<template>
  <div id="app">
    <img alt="Jokan logo" src="./assets/logo.png" height="200" weight='200' >
    <HelloWorld msg="Jikan Moe"/>
    <Anime />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Anime from './components/Anime.vue'
export default {
  name: 'App',
  components: {
    HelloWorld,
    Anime
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
  background-color: aquamarine;
}
</style>
