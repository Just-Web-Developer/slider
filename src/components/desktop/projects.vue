<template>
  <div class="projects" @wheel.stop="slideHandler($event)">
    <projectsWrappers :slide="slide" @nextSlide="nextSlideHandler()" @nav="$emit('nav')" @goHome="$emit('goHome')"/>

    <projectsSlide1 />
    <projectsSlide2 :currentSlide="currentSlide" />
    <projectsSlide3 @contact="$emit('contact')"/>
  </div>

</template>

<script>
import projectsWrappers from "./projects/projectsWrappers";

import projectsSlide1 from "./projects/projectsSlide1";
import projectsSlide2 from "./projects/projectsSlide2";
import projectsSlide3 from "./projects/projectsSlide3";


export default {
  name: "Agency",
  props:['slide'],
  components:{
    projectsWrappers,
    projectsSlide1,
    projectsSlide2,
    projectsSlide3
  },
  emits:['goHome', 'nav', 'contact', 'nextSlide'],
  data(){
    return{
      currentSlide:0,
      max:5,
      scrolling:false
    }
  },
  methods:{
    nextSlideHandler(){
      if (this.slide === 2 && this.currentSlide < this.max){
        this.currentSlide++
      }
      else{
        this.$emit('nextSlide')
        this.currentSlide = 0
      }
    },
    prevSlideHandler(){
      if (this.slide === 2 && this.currentSlide > 0){
        this.currentSlide--
      }
      else{
        this.$emit('prevSlide')
        this.currentSlide = 0
      }
    },
    slideHandler(e){
      if (this.scrolling === false){
        if (e.deltaY > 0){this.nextSlideHandler()}
        if (e.deltaY < 0){this.prevSlideHandler()}
        this.scrolling=true
        setTimeout(()=>{this.scrolling=false},500)
      }

    }
  }
};
</script>

<style scoped>
.projects > .slide{
  width: 100vw;
  height: 100vh;
}
</style>
