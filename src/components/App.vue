<template>
  <div id="app">
      <h1>Online contacts</h1>
    <contact-card v-on:add="addcontact"/>
      <div class="separation"></div>
   <contact-list v-bind:contacts="userlist" v-on:editSpecific = "changeValues" v-on:editTrue = "editStatus"/>
  </div>
</template>

<script>
    import contactCard from "./Createcontact.vue"
    import contactbook from "./ShowContacts.vue"
    export default {
        name: 'app',
        components: {
            "contact-card": contactCard,
            "contact-list": contactbook
        },
        data: function() {
            return {
                userlist: []
            }
        },
        methods: {
            addcontact: function(obj) {
                console.log("hej");

                this.userlist.push(obj);
                console.log(this.userlist);
            },
            changeValues: function(index, obj) {
                console.log(obj);
                for (let i = 0; i < this.userlist.length; i++) {
                    if (i === index) { 
                        
                        let savedUrl = obj.Url;
                        let savedName = obj.Name;
                        let savedEmail = obj.Email;
                        let savedAge = obj.Age;
                        let savedEdit = obj.Edit;
                        
                        
                        this.userlist[i].Url = savedUrl;
                        this.userlist[i].Name = savedName;
                        this.userlist[i].Email = savedEmail;
                        this.userlist[i].Age = savedAge;
                        
                        
                       
                    }
                }
            },
            editStatus: function(index,status) {
                console.log(index);
                console.log(status);
                 for (let i = 0; i < this.userlist.length; i++) {
                    if (i === index) {
                    
                    this.userlist[i].Edit = status;
                    
                    }
            }
        }
    }
    }
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>
    body {
        background: url(https://images.pexels.com/photos/205414/pexels-photo-205414.jpeg?auto=compress&cs=tinysrgb&dpr=2&h=750&w=1260);
        background-repeat: no-repeat;
        background-position: center center;
        background-attachment: fixed;
        -webkit-background-size: cover;
        -moz-background-size: cover;
        -o-background-size: cover;
        background-size: cover;
        z-index: -1;
    }

    label {
        opacity: 0.9;
    }
</style>

<style scoped>
    h1 {
        color: white;
        opacity: 0.9;
        font-size: 3rem;
    }

    .separation {
        width: 75vw;
        height: 6px;
        background-color: black;
        margin-top: 30px;
        margin-bottom: 20px;
        opacity: 0.9;
    }

    #app {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>