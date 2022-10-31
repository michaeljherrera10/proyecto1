<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <newProject msg=""/>
  </div>
</template>

<script>
import newProject from './components/newComponents.vue';

export default {
  name: 'App',
  components: {
    newProject
  }
}
</script>

<style>
@import "assets/style.css";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>