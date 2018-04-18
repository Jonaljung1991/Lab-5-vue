<template>
    <div class="book1">
           <div class="book" v-for="contact in contacts">
           <div class="imgContainer">
            <img :src ="contact.Url">
            </div>
               <div class="position">
                   <div>
                       <span>Name</span><p>{{ contact.Name }}</p>
                       </div>
                   <div>
           <span>Email</span><p>{{ contact.Email }}</p>
                       </div>
                   <div>
          <span> Age</span><p>{{ contact.Age }}</p>
                       </div>
                   </div>
       </div>
   
       
       
       
    </div>
</template>

<script>
    export default {
        props: ['contacts'],
        data: function() {
            return {

            };
        } // data
    }
</script>

<style scoped>
    .book1 {
        width: 80vw;
        display: flex;
        justify-content: center;
        flex-wrap: wrap;
    }

    .book {
        display: flex;
        margin-top: 30px;
        height: 160px;
        width: 40%;
        color: black;
        border-style: solid;
        border-width: 3px;
        border-color: white;
        padding: 25px;
        box-shadow: 4px 2px 4px 2px gray;
        background-color: #f4f4f4;
        border-radius: 4px;
        font-family: arial;
        margin: 10px;
    }

    .imgContainer {
        width: 40%;
        height: 100%;
    }

    .imgContainer img {
        width: 100%;
        height: 100%;
    }

    .position {
        margin: 0 40px;
        font-size: 1.25rem;
        flex: 1;
        flex-direction: column;
        justify-content: space-around;
        display: flex;
    }

    .position div {
        display: flex;
        align-items: center;
    }

    .position div p {
        border-bottom: 1.5px solid black;
        flex: 1;
        margin-left: 10px;
    }
</style>