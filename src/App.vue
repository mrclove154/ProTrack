<template>
  <div id="app">
    <navbar />
    <sidebar />
  </div>
</template>

<script>
import axios from "axios"
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
          isOpen: false
    }
    }
  }

</script>

<style lang="scss">

</style>
