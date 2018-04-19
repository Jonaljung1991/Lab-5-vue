<template>

    <div class="cardBody">
    <button v-on:click ="isEditable">Add new contact</button>
    <div class="upperSection">
    <div class ="picturebody">
    <img :src="imgUrl">
    </div>
    <div class="edit">
    <label id="editMe">Create contact
    <input type="checkbox" for="editMe" v-model = "editable" >
        </label>
    </div>
        </div>
    <div class="lowerSection">
    <div class="editTrue" v-if="editable">
            <div><label id="url">ImgURL</label> <input type="text" for="url" v-model="imgUrl"></div>
            <div><label id="name">Name</label><input type="text" for="name" v-model="name"></div>
            <div><label id="email">Email</label> <input type="text" for="email" v-model="email"></div>
            <div> <label id="age">Age</label> <input type="text" for="age" v-model="age"></div>
    </div>
    <div class="editFalse" v-else="editable">
    
            <div><span>Name </span><p>{{name}}</p></div>
            <div><span>Email </span>  <p>{{email}}</p></div>
        <div><span>Age </span> <p> {{age}}</p></div>
    </div>
    </div>
</div>

</template>




<script>
    export default {
        props: [],
        data: function() {
            return {
                editable: false,
                imgUrl: " https://cdn.pixabay.com/photo/2016/08/31/11/54/user-1633249__340.png",
                name: "",
                email: "",
                age: "",
                id : 0
            }
        },
        methods: {
            isEditable: function(event) {
                let url = (this.imgUrl);
                let name = (this.name);
                let email = (this.email);
                let age = (this.age);
                let id = (this.id);
                
                this.$emit("add", {
                    Url: url,
                    Name: name,
                    Email: email,
                    Age: age,
                    Edit : false,
                    Id : id
                })
                console.log(this.id);
                this.id += 1;
            }
        }
    };
</script>


<style scoped>
    .cardBody * {
        margin: 0;
    }

    .cardBody {
        opacity: 0.9;
        display: flex;
        flex-direction: column;
        width: 400px;
        height: 250px;
        padding: 25px;
        border-radius: 4px;
        box-shadow: 2px 4px 7px 3px black;
        background-color: white;
    }

    .upperSection {
        display: flex;
        z-index: 1;
        align-items: flex-start;
        border-bottom: 3px solid black;
        padding-bottom: 25px;
    }

    .picturebody {
        width: 70px;
        height: 70px;
        display: inline-block;
    }

    .picturebody img {
        width: 100%;
        height: 100%;
    }

    .edit {
        margin-left: auto;
        align-self: flex-start;
        display: inline-block;
        padding: 10px;
        font-size: 1.25rem;
    }

    .edit input[type=checkbox] {
        width: 20px;
        height: 20px;
        margin-left: 10px;
        vertical-align: middle;
    }

    .lowerSection {
        display: flex;
        flex-direction: column;
        flex: 1;
        justify-content: center;
        padding-top: 25px;
    }

    .lowerSection div span {
        flex: 1;
        align-self: center;
    }

    .lowerSection div p {
        flex: 3;
        display: inline-block;
        border-bottom: 1.5px solid black;
    }

    .lowerSection .editTrue,
    .editFalse {
        display: flex;
        flex: 1;
        flex-direction: column;
        justify-content: center;
        padding: 20px;

    }

    .editFalse>div {
        display: flex;
        flex-direction: row;
        align-items: center;
        padding: 1em;
    }

    .editTrue div {
        display: flex;
        justify-content: flex-end;
        align-items: center;
        padding: 0.85em;
    }


    .editTrue label {
        flex: 1;
    }

    .editTrue input {
        flex: 3;
        border-style: none;
        border-bottom: 1.5px solid black;
        outline: none;
        background-color: white;
    }
    button {
        width: 25%;
        height: 45px;
        border-radius: 4px;
        align-self: flex-end;
        background-color: lightgreen;
        color: black;
        font-size: 1.1rem;
        border-style: none;
        opacity: 0.9;
    }
</style>