<template>
  <div>
    <div v-show="value">
        <transition name="modal">
            <div class="overlay" @click.self="isOpen = false;">
                        <div class="modal">
                        <div slot="header">Create Issue</div>
                                <div slot="body">
                                    <form>
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Organization" v-model="formdata.Organization">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Project_name" v-model="formdata.Project_name">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Description" v-model="formdata.Description">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Issue_Type" v-model="formdata.Issue_Type">  
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Priority" v-model="formdata.Priority">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Tags" v-model="formdata.Tags">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Assigned_by" v-model="formdata.Assigned_by">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Assigned_to" v-model="formdata.Assigned_to">                                
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Effort_hours" v-model="formdata.Effort_hours">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Due_date" v-model="formdata.Due_date">
                                        <input type="text" style="padding:7px; margin:6px; width:80%;" class="form-field selenium-project-name" placeholder="Links" v-model="formdata.Links">
                                    </form>
                                
                                </div>
                                <div slot="footer">
                                    <button style="width:15%" @click="saveData()">
                                        Save
                                    </button>
                                    <button  @click.prevent="close" style="width:15%" @click="isOpen = false">
                                        Cancel
                                    </button>
                                </div>
                        </div>
                    </div>
        </transition>
    </div>
  </div>
</template>

<script>
import axios from "axios"
export default {
    props: {
        value: {
            required: true
        }
    },
  data: function() {
    return {
       isOpen: true,
    "formdata": {"Organization": "",
    "Project_name": "",
    "Description": "",
    "Issue_Type": "",
    "Priority": "",
    "Tags": "",
    "Assigned_by": "",
    "Assigned_to":"",
    "Effort_hours": "",
    "Due_date": "",
    "Links": ""}
    };
  },
   "methods":{ saveData() {
    //  let headers = {"x-api-key": "NjGejFGHCF6T4MNGnDV8l4QntlXmdoOS7SnamcOT"}
                console.log(this.formdata)
                axios.post("https://tcss9jr2wf.execute-api.us-west-2.amazonaws.com/Test", null, {

                    "params": {"config": this.formdata},
                    "headers": {"Content-Type": "application/json"}

                }).then(response => {

                   console.log(response)
                })
                    

            this.formdata = {}
          
   },
   close() {
          this.$emit("input", !this.value);
        }
   }
};
</script>

<style scoped>
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
  padding: 7px;
  margin-top: 10px;
  background-color: green;
  color: white;
  font-size: 1.1rem;
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