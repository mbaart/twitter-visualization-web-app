<template>
  <div id="app">
    <marquee>Follow for Follow: A Bird's Eye View.             Data Visualization Project.              SENG 480D, Spring 2019               Taught by Dr. Charles Perrin</marquee>
    <swiper ref="mySwiper" :options="swiperOption">
      <!-- slides -->
      <swiper-slide>
        <DV1/>
      </swiper-slide>
      <swiper-slide>
        <DV2/>
      </swiper-slide>
      <swiper-slide>
        <DV3/>
      </swiper-slide>

      <!-- <p v-if="swiper.activeIndex() === 1"> test </p> -->

      <!-- Optional controls -->
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    <transition mode="out-in" name="fade">
      <p v-if="curSlide == 0">This is the first visualization: <br> For our first visualization, we used 55 different colors to easily identify this huge pile of garbage dataset. Amazing! <br> Click on anything to see nothing happen.</p>
    </transition>
    <transition mode="out-in" name="fade">
      <p v-if="curSlide == 1">This is the second slide paragraph</p>
    </transition>
    <transition mode="out-in" name="fade">
      <p v-if="curSlide == 2">This is the third slide paragraph</p>
    </transition>
  </div>
</template>
<script>
import "swiper/dist/css/swiper.css";
import { swiper, swiperSlide } from "vue-awesome-swiper";
import DV1 from "./components/DV1.vue";
import DV2 from "./components/DV2.vue";
import DV3 from "./components/DV3.vue";

export default {
  name: "app",
  components: {
    swiper,
    swiperSlide,
    DV1,
    DV2,
    DV3
  },
  data() {
    return {
      curSlide: 0,
      swiperOption: {
        direction: "horizontal",
        pagination: {
          el: ".swiper-pagination",
          type: "bullets"
        }
      }
    };
  },

  computed: {
    swiper() {
      return this.$refs.mySwiper.swiper;
    }
  },

  mounted() {
    // current swiper instance
    // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
    console.log(
      "this is current swiper instance object",
      this.swiper.activeIndex
    );

    this.swiper.on("slideChange", () => {
      this.curSlide = this.swiper.activeIndex;
    });
  }
};
</script>

<style>
body {
  margin: 0;
  padding: 0;
  background-color: #dff9fb;
}

marquee {
  font-size: 2em;
  color: #95afc0;
  font-family: Lucida Sans Typewriter, Lucida Console, monaco,
    Bitstream Vera Sans Mono, monospace;
}

#app {
  width: 100%;
  height: 100%;
  margin: 0;
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.swiper-slide {
  display: flex;
  justify-content: center;
  flex-direction: row;
}

.swiper-pagination {
  position: absolute;
  float: bottom;
  bottom: 5%;
}

.container {
  display: flex;
  flex-direction: column;
}

p {
  font-size: 1.5em;
  color: #95afc0;
  position: absolute;
  left: 5%;
  bottom: 10%;
  text-align: left;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
