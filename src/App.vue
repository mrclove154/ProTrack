<template>
  <div id="app">
    <navbar></navbar>
    <sidebar></sidebar>
  </div>
</template>

<script>
import sidebar from "./components/sidebar"
import navbar from "./components/navbar"

export default {
  name: 'app',
  "components": {
        sidebar,
        navbar
    },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
