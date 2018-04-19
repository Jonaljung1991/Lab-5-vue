<template>
    <div class="book1">
           <div class="book" v-for="(contact,index) in contacts" :key ="contact.Id">
           <div class="imgContainer">
            <img :src ="contact.Url">
            </div>
            <div class="position">
                   <div class="edit">   
                        <label id="editMe">Edit
                            <input type="checkbox" for="editMe" @click="isEditable(index)"  v-model="checked">
                        </label>
                        </div>
                <div class="edittrue"  v-if="contact.Edit"> 
                    <div><button @click="editcard(index)">Save</button></div>
                    <div><label id="url">ImgURL</label> <input type="text" for="url" v-model="contact.imgUrl"></div>
                    <div><label id="name">Name</label><input type="text" for="name" v-model="contact.name"></div>
                    <div><label id="email">Email</label> <input type="text" for="email" v-model="contact.email"></div>
                    <div> <label id="age">Age</label> <input type="text" for="age" v-model="contact.age"></div>
                   
                </div>
                
                <div class="editfalse" v-else="contact.Edit">
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
    </div>
</template>

<script>
    export default {
        props: ['contacts'],
        data: function() {
            return {
                checked: null,
                imgUrl: " https://cdn.pixabay.com/photo/2016/08/31/11/54/user-1633249__340.png",
                name: "",
                email: "",
                age: ""
            };
        },
        methods: {
            isEditable : function(index){
                console.log(this.checked);
                    if (this.checked === true) {
                       
                        this.$emit("editTrue",index,true)
                    } else {
                           this.$emit("editTrue",index,false)
                    }
            },
            editcard: function(index) {
                    this.$emit("editSpecific" ,  index , {
                        Url :this.imgUrl,
                        Name : this.name,
                        Email : this.email,
                        Age : this.age
                       
                    })
                }
            }
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
        opacity: 0.9;
        display: flex;
        margin-top: 30px;
        height: 200px;
        width: 40%;
        color: black;
        border-style: solid;
        border-width: 3px;
        padding: 25px;
        box-shadow: 2px 4px 7px 3px black;
        background-color: #e6f2ff;
        border-radius: 4px;
        font-family: arial;
        margin: 10px;
    }
    
    .book button {
        width: 50px;
        height: 30px;
        background-color: red;
        margin: 10px;
/*        align-self: flex-end;*/
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
        font-size: 1.25rem;
        flex: 1;
        flex-direction: column;
        justify-content: space-around;
        display: flex;
        /*        border: 1.5px solid black;*/
        padding: 10px;
    }

    .edittrue {
         display: flex;
        flex: 1;
        flex-direction: column;
        justify-content: center;
        padding: 20px;

    }
    
    .edittrue div {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        padding: 0.85em;
    }

    

    .edit {
        display: flex;
        flex-direction: column;
        justify-content: center;
    }

    .edit label {
        align-self: flex-end;
        opacity: 0.9;
    }

    .edit input {
        width: 15px;
        height: 15px;
    }

    /*
    .position div {
        display: flex;
        align-items: center;
    }
*/

    .position div p {
        border-bottom: 1.5px solid black;
        flex: 1;
        margin-left: 10px;
    }
</style>