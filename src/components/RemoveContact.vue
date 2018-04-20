<template>
<button @click="remove">Remove</button>
</template>

<script>
export default {
    methods: {
        remove:function(){
            this.$emit("removethis");
        }
    }
}
</script>

<style scoped>
    button{
     width: 90px;
        height: 35px;
        background-color: #ff471a;
        border-style: none;
        border-radius:4px;
        font-size: 1.1rem;
       font-family: Tahoma,Geneva,sans-serif;
    }
    
    button:hover{
        background-color: #e62e00;
    }
        

</style>