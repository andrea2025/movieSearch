<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <HelloWorld msg="Welcome to Your Vue.js App"/>
     
    <toDoList/>
    <movieSearch/>
   
  </div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import mycomponent from './components/mycomponent.vue'
//import form1 from './components/form1.vue'
//import memories from './components/memories.vue'
//import contactform from './components/contactform.vue'
//import toDoList from './components/toDoList.vue'
import movieSearch from './components/movieSearch.vue'

export default {
  name: 'app',
  components: {
    movieSearch

  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
