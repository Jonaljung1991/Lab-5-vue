<template>
    <div class="book1">
           <div class="book" v-for="(contact,index) in contacts" :key ="contact.Id">
           <div class="imgContainer">
            <img :src ="contact.Url">
            </div>
            <div class="position">
                   <div class="edit">   
                        <label id="editMe">Edit
                            <input type="checkbox" for="editMe" @click="isEditable( $event ,index)">
                        </label>
                        </div>
                <div class="edittrue"  v-if="contact.Edit"> 
                    <div class="posButton"><button @click="editcard(index , contact.imgUrl, contact.Name , contact.Email, contact.Age)">Save</button></div>
                    <div><label id="url">ImgURL</label> <input type="text" for="url" v-model="contact.imgUrl"></div>
                    <div><label id="name">Name</label><input type="text" for="name" v-model="contact.Name"></div>
                    <div><label id="email">Email</label> <input type="text" for="email" v-model="contact.Email"></div>
                    <div> <label id="age">Age</label> <input type="text" for="age" v-model="contact.Age"></div>
                   
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
                imgUrl: " https://cdn.pixabay.com/photo/2016/08/31/11/54/user-1633249__340.png",
                name: "",
                email: "",
                age: ""
            };
        },
        methods: {
            isEditable: function(event, index) {
                if (event.target.checked) {
                    this.$emit("editTrue", index, true)

                } else {
                    this.$emit("editTrue", index, false)
                }
            },
            editcard: function(index, url, name, email, age) {
                console.log(index);
                console.log(url);
                console.log(name);
                console.log(email);
                console.log(age);
                this.$emit("editSpecific", index, {
                    Url: url,
                    Name: name,
                    Email: email,
                    Age: age

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
     .position .edittrue .posButton{
        display: flex;
        justify-content:flex-end;
        margin-top:20px;
    }
    .book button {
        width: 70px;
        height: 30px;
        background-color: lightgreen;
        border-style: none;
        border-radius:4px;
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
        padding: 10px;
    }
    .editfalse{
        margin-left: 30px;
    }
    .edittrue {
        display: flex;
        flex-direction: column;
        justify-content: center;

    }

    .edittrue div {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        padding:0.85em 0 ;
    }

    .edittrue div label {
    }

    .edittrue div input{
        width: 55%;
        margin-left: 30px;
        border-style:none;
        border-bottom: 1.5px solid black;
        background-color: #e6f2ff;
        outline: none;
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