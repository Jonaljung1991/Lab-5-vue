<template>
  <div id="app">
      <h1>Online-contacts</h1>
    <contact-card v-on:add="addcontact"/>
   <contact-list v-bind:contacts="userlist"/>
  </div>
</template>

<script>
    import contactCard from "./Createcontact.vue"
    import contactbook from "./ShowContacts.vue"
    export default {
        name: 'app',
        components: {
            "contact-card": contactCard,
            "contact-list":contactbook
        },
        data:function(){
            return {
                userlist : []
            }
        },
        methods:{
            addcontact:function(obj){
                console.log("hej");
              
                this.userlist.push(obj);   
                   console.log(this.userlist);
            }
        }
    }
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>

</style>

<style scoped>
    #app{
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    
</style>