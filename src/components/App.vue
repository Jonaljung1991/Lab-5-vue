<template>
  <div id="app">
    <contact-card v-on:add="addcontact"/>
  </div>
</template>

<script>
    import contactCard from "./Createcontact.vue"
    export default {
        name: 'app',
        components: {
            "contact-card": contactCard, 
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
</style>