<template>
  <div id="app">
    <navbar />
    <!-- <header /> -->
    <sidebar />
  </div>
</template>

<script>
import axios from "axios"
import sidebar from "./components/sidebar"
import navbar from "./components/navbar"
import header from "./components/header"

export default {
  name: 'app',
  "components": {

        sidebar,
        navbar,
        header
    },
  data () {
    return {
    }
  }
}
</script>

<style lang="scss">
// #app {
//   font-family: 'Avenir', Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }
</style>
