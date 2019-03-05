<template>
  <div class="about">
    <h1>
      About
    </h1>
    <p> {{ msg }} </p>
  </div>
</template>

<script>
export default {
  name: 'About',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
