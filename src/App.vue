<template>
  <div id="app">
  <carousel-3d  :height="slideHeight" :width="500" :controls-visible="true" :controls-prev-html="'&#10092; '" :controls-next-html="'&#10093;'" 
               :controls-width="30" :controls-height="60" :clickable="false">
    <slide v-for="(slide, i) in slides" :key="i" :index="i">
      <img :src="images[i]"/>
    </slide>
  </carousel-3d>
</div>
</template>

<script>
import {Carousel3d, Slide } from 'vue-carousel-3d';

export default {
  name: 'App',
  components: {
    Carousel3d,
    Slide
  },
  data: function() {
    return {
      slides: 5,
      slideHeight: 500,
      images:["hi.png","why.jpg"]
    }
  },
  methods:{
    getViewHeight(){
      this.slideHeight = window.innerHeight-100;
    }
  },
  mounted(){
    this.getViewHeight()
  }
}
</script>

<style>
body{
  background-color: black;
}
</style>
