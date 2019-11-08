<template>
   <div>
        <form @submit.prevent="submitForm">
        <div class="form_item">
            <label for="name">Fullname:</label>
             <input type="text" v-model="newUser.fullName">
        </div>
        <div class="form_item">
            <label for="email">Email:</label>
            <input type="text" v-model="newUser.email">
        </div>
        <button>Submit</button>
       
        <button @click.prevent="clearform" >clear</button>
    </form>
    <table>
        <thead>
        <tr v-for="user in allUsers" :key="user">
            <th>fullname</th>
            <th>email</th>
        </tr>
        </thead>
        <tbody>
        <tr>{{newUser.fullName}}</tr></tbody>
        <tr>{{newUser.email}}</tr>
    </table>
   </div>
</template>
<script>
export default {
    name :'form1',
    data (){
        return{
            newUser:{
                fullName:'',
                email:''
            },
            allUsers:[]
        }
    },
    methods: {
        submitForm(){
            this.allusers.push(this.newUser)
            this.clearform
        },
        clearform(){
           this.newUser;{
                this.fullName = '',
                 this.email = ''
           }
        }
    },
}
</script>
<style scoped>
form {
    max-width: 400px;
    background: tan;
    margin: 0 auto;
    padding: 2rem;

}
.form_item{
    margin-bottom: 1rem;
    width: 100;
    display: block;
}
.form_item > input{
    padding: 10px;
}
.form_item > label{
    font-size:24px;
    display: block;
}
button{
    background:silver;
    border: none;
    border-radius: 20px;
    font-size: 20px;
    color:#fff;
    padding: 5px 15px;
}
table{
    border: 1px solid blue;
}
</style>