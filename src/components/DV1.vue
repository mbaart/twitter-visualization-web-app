<template>
  <div class="container">
    <svg ref="dv" width="500" height="300"></svg>
    <p>{{msg}}</p>
  </div>
</template>

<script>
const d3 = require("d3");
export default {
  name: "DV1",
  props: {
    msg: String
  },

  mounted: function() {
    // this.#el - is the root element in <template>
    // in this case it is <svg> tag
    d3.select(this.$refs.dv)
      .append("circle")
      .attr("cx", "250")
      .attr("cy", "150")
      .attr("r", "100");
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>