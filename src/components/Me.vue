<template>
  <div id="me">
    <div class="row">
      <img class="picture" :class="{flip: isFlipped}" :src="require('../assets/people/' + name + '.jpg')"/>
      <div class="descripton"> 
        <h1> {{ name }} </h1>
        <p> {{ description }} </p>
      </div>
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
    isFlipped: Boolean,
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
        width: 50%;
    }
    
    .picture.flip {
      float: right;
    }

    .row:after {
      content: "";
      display: flex;
      clear: both;
    }
</style>
