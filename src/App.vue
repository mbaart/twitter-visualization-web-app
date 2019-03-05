<template>
  <div id="app">
    <About msg="This is our project blah, blah, blah..."/>
    <ul v-for= "(person, index) in people" :key = index>
      <Me :isFlipped="(index % 2 == 0)"   :name=person.name :description=person.description />
    </ul>
  </div>
</template>

<script>
import About from './components/About.vue'
import Me from './components/Me.vue'
import members from './assets/members.json'

export default {
  name: 'app',
  components: {
    About,
    Me
  },
  data(){
    return{
      people: members.people
    }
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
