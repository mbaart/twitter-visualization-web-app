<template>
  <div id="me">
    <h1> Who we are. </h1>
    <img class="picture" :src="require('../assets/' + name + '.jpg')"/>
    <div class="descripton"> 
      <h1> {{ name }} </h1>
      <p> {{ description }} </p>
    </div>
  </div>
</template>

<script>
// import Vue from 'vue'
export default {
  name: 'Me',
  props: {
    name: String,
    description: String,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
    #me{
        width: 100%;
        /* margin: 10%; */
    }

    .picture {
        float: left;
        width: 40%;
    }

    .description {
        float: left;
        width: 60%;
    }
</style>
