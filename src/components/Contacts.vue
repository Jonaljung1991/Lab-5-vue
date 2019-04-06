<template>
    
    <div class="contactContainer">
        <h2>{{heading}}</h2>
            <div class="listContact"> 
                <ul class="lol">
                    <li>
                         <p id="name">Name: {{ contactName }} </p>
                         <p id="email">Email: {{ contactEmail }}</p> 
                         <p id="age">Age: {{ contactAge }}</p> 
                        <input class="radioBtn" type="checkbox" v-model="checkedLi">
                        <!--<label for="checkbox">{{ checked }}</label>-->
                    </li>
                    
                     <li>
                         <p id="name">Name: {{ contactName }} </p>
                         <p id="email">Email: {{ contactEmail }} </p>
                         <p id="age">Age: {{ contactAge }} </p>
                        <input class="radioBtn" type="checkbox" value="on"  v-on:click="showBtns">
                    </li>
                    <span>Checked : {{ checkedLi }}</span>
                </ul>
        </div>
    </div>
</template>

<script>
export default {
    data: function(){
        return { 
            heading:"Your Contacts :",
            showButtons: '',
            contactName: "Bengt",
            contactEmail: "benganGbg@hej.com",
            contactAge: "39",
            checkedLi: []
            
        }
    },
    methods: {
        showBtns: function(event) {
            //event.target()
            this.contactName = "lol"
            
        }
    }
};
</script>

<!-- CSS libraries -->
<style src="normalize.css/normalize.css"></style>

<!-- Global CSS -->
<style>

</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
    h2 {
        color: white;
        text-align: center;
    }
    .listContact {
        height: 400px;
        height: 600px;
        background-color: royalblue;
        padding: 30px;
    }
   
    .lol > li {
        display: table;
        vertical-align: middle;
        display: table-cell;
        margin-left: 20px;
        margin-top: 20px;
        background-color: #002699;
        color: rgb(0, 38, 153);
        color: white;
        width: 400px;
        height: 200px;
        border-style: solid;
        border-radius: 10px;
        border-width:4px;
        border-collapse: white;
    }
    
    .listContact li p {
        margin-left: 30px;
    }
    
    .radioBtn {
        margin-left: 30px;
        background-color: green;
    }
</style>