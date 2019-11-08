<template>
    <div>
        <h1>{{title}}</h1>
        <div>
            <input type="text" name="#" v-model="newItem.listItem" placeholder="list of things to do">
            <button  @click.prevent="btn">add+</button>
        </div>
        <table>
            <thead>
                <tr>
                    <td>to do list </td>
                    <td>delete</td>
                </tr>
            </thead>
            <tbody>
                <tr  v-for="list in listRoll" :key="list">
                    <td>{{list.listItem}}</td>
                    <td><button @click="del(index)">delete</button></td>
                </tr>
            </tbody>
        </table>
        <h2>total item(s):{{x}}</h2>
        <h2>total deleted:{{z}}</h2>
    </div>
</template>
<script>
export default {
    name:'toDoList',
    data() {
        return {
            newItem:{ listItem:""},
            listRoll:[],
             title:"To do list",
             z:0

        }

       
    },
    methods:{
        btn(){
            this.listRoll.push(this.newItem)
            this.newItem = {listItem:" "}

        },
        del(index) {
        this.listRoll.splice(index,1),
        this.z=this.z +1
    }
    },
    computed:{
        x(){
            //let total  = 0;
            //this.listRoll.filter(list => total = total * list.listItem)
            return this.listRoll.length;
        }
        
    }
}
</script>
<style scoped>
*{
    font-weight: bold;
}
input{
    padding: 1rem;
    border-radius: 20px;
    width: 50%;
    background: white;
}
button{
    border-radius:20px;
    background: darksalmon;
    font-size: 15px;
    padding: 10px;
    color:wheat;
}
table {
  border: 1px solid black;
  border-collapse: collapse;
  width: 60%;
  color:crimson;
  margin: 2rem auto;
}
td, th {
  border: 1px solid #3333;
  padding: 0.5rem;
  background: #dbdbdb;
}
tr:nth-child(even) {
background: #dbdbdb;
}
</style>