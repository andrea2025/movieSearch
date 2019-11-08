<template>
  <div id="app">
    <input type="text" v-model="newName" />

    <button @click="add">Add</button>
    <div>
      <p v-for="list in nameList" :key="list" v-html="list.name"></p>
    </div>
  </div>
</template>
<script>
export default {
  name: "memories",
  data() {
    return {
      nameList: [{ name: "oge" }],
      newName: " "
    };
  },

  methods: {
    add() {
      return this.nameList.push({ name: this.newName });
    }
  }
};
</script>
<style scoped>
*{
    color:brown;
    font-size: 20px;
}
button{
    background: yellowgreen;
    padding:10px 20px;
    border-radius:20px;
    border:none;
    margin-left: 2rem;
}
input{
    padding: 10px;
}
</style>