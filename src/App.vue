<template>
  <div id="app">
    <img class="logo" alt="Vue logo" src="./assets/logo.png">
    <ButtonCreator msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import ButtonCreator from './components/ButtonCreator.vue'

export default {
  name: 'app',
  components: {
    ButtonCreator
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

.logo {
  height: 50px;
}
</style>
