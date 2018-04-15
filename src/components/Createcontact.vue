<template>

<div>
<ul>
<li>{{name}}</li>
    <li>{{email}}</li>
    <li>{{age}}</li>
</ul>    
</div>

</template>




<script>
export default {
    data: function(){
        return{
            name:"Jonathan",
            email:"jontecoolboy@blabla.com",
            age:"12"
        }
    }
};

</script>


<style scoped>
    div{
        width: 100vw;
        height: 15vh;
        background-color: powderblue;
    }
    ul{
        list-style: none;
    }
</style>

