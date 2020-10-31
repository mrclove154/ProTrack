<template>
    <div id="app">
      <header class="header">
       <div class="navbar">
            <a class="active" href="#home">Home</a>
            <a href="#news">News</a>
            <a href="#contact">Contact</a>
            <modal v-model="isOpen"></modal>
            <button @click="isOpen = !isOpen">
                Create
              </button>

        </div>
      </header>
    </div>
</template>

<script>
import axios from "axios"
import modal from "./Modal"

export default {
  "components": {

        modal
    },
  data () {
    return {
    isOpen: false
    }
   
  },
   "methods":{ 
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

body{
    margin:0;

}

.navbar {
  background-color: #333;
  overflow: hidden;
  // background-image: url('http://upload.wikimedia.org/wikipedia/commons/6/6b/Bubble_3.jpg');

  
}
.navbar a {
  float: left;
  color: #f2f2f2;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
  font-size: 17px;
  height: 50px;
}
.navbar a:hover {
  background-color: #ddd;
  color: black;
}
.navbar a.active {
  background-color: #4CAF50;
  color: white;
}
button {
  padding: 5px;
  margin-top: 20px;
  background-color: blue;
  color: white;
  font-size: 1rem;
  width: 7%;
}

</style>
