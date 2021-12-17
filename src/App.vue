<template>
  <div id="app">
    <div class="logo">
      <img src="./assets/spotify.png" alt="logo_spotify">
    </div>
    <Records/>
  </div>
</template>

<script>
import Records from './components/Records.vue'
export default {
  name: 'App',
  components: {
    Records,
  
  }
}
</script>

<style lang="scss">
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #1e2d3b;
  height: 100vh;
  width: 100vw;
  .logo {
    height: 70px;
    padding: 10px 20px;
    background-color: #2e3a46;
    img {
      height: 100%;
    }
  }
  
}
</style>
