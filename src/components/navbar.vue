<template>
    <div id="app">
      <header class="header">
       <div class="navbar">
            <a class="active" href="#home">Home</a>
            <a href="#news">News</a>
            <a href="#contact">Contact</a>
            <!-- <a href="#about">About</a> -->
            <!-- <button style="width:10%; margin:23px; padding:5px;">
                Create
            </button> -->
            <div>
              <transition name="modal">
                <div v-if="isOpen">
                  <div class="overlay" @click.self="isOpen = false;">
                    <div class="modal">
                      <!-- <h1>Modal heading</h1>
                      <p>This my first modal using vue.js</p> -->
                      <div slot="header">Create Issue</div>
                            <div slot="body">
                                <form>
                                    <input type="text" style="padding:7px; margin:10px; width:80%;" class="form-field selenium-project-name" placeholder="Project" v-model="project">
                                    <input type="text" style="padding:7px; margin:10px; width:80%;" class="form-field selenium-project-name" placeholder="Issue Type" v-model="issue">
                                     <input type="text" style="padding:7px; margin:10px; width:80%;" class="form-field selenium-project-name" placeholder="Summary" v-model="summary">
                                    <input type="text" style="padding:7px; margin:10px; width:80%;" class="form-field selenium-project-name" placeholder="Description" v-model="desc">                                
                                </form>
                              
                            </div>
                            <div slot="footer">
                                <button style="width:15%" @click="saveData()">
                                    Save
                                </button>
                                <button style="width:15%" @click="isOpen = false">
                                    Cancel
                                </button>
                            </div>
                    </div>
                  </div>
                </div>
              </transition>
              <button @click="isOpen = !isOpen;">
                <!-- {{ isOpen ? "Close" : "Open" }} modal -->
                Create
              </button>
            </div>
        </div>
      </header>
    </div>
</template>

<script>
import axios from "axios"
export default {
  data () {
    return {
    isOpen: false,
    "project": "",
    "issue": "",
    "summary": "",
    "desc": ""
   }
  },
   "methods":{ saveData() {
     let url = "https://7uo4j8nk6c.execute-api.ap-south-1.amazonaws.com/mridul/upload2"
            axios({"method": "post",
                "url": url,
                "data": null,
                "params": {"blog_title": this.blogtitle,
                    "blog_data": this.blogdata},
                "headers": {"Content-Type": "application/json"}}).then(function () {

                alert("Your blog has been uploaded")
                // window.location.reload()

            }).
                catch(function () {

                    alert("can't upload file")

                })
            this.project = ""
            this.issue = ""
            this.summary = ""
            this.desc = ""
   }}
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

.navbar {
  background-color: #333;
  overflow: hidden;
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
.modal {
  width: 500px;
  margin: 0px auto;
  padding: 20px;
  background-color: #fff;
  border-radius: 2px;
  box-shadow: 0 2px 8px 3px;
  transition: all 0.2s ease-in;
  font-family: Helvetica, Arial, sans-serif;
}
.fadeIn-enter {
  opacity: 0;
}

.fadeIn-leave-active {
  opacity: 0;
  transition: all 0.2s step-end;
}

.fadeIn-enter .modal,
.fadeIn-leave-active.modal {
  transform: scale(1.1);
}
button {
  padding: 5px;
  margin-top: 20px;
  background-color: blue;
  color: white;
  font-size: 1rem;
  width: 7%;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: #00000094;
  z-index: 999;
  transition: opacity 0.2s ease;
}
</style>
