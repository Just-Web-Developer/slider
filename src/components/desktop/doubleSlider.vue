<template>
  <div class="slider flex">
    <div class="left mr-10 flex flex-col">
      <div class="mini-slide relative w-120 h-83 overflow-hidden">
        <transition :name="sliderDirection" v-for="(item, index) in text.images" :key="item + index">
          <img v-if="additionalSlide === index" class="unselectable absolute left-0 w-120 h-83" :src="require('@/assets/images/' + src + '/01/slider/' + item + '.png')" alt="">
        </transition>
      </div>
      <div class="arrows flex justify-end mt-10 mb-25">
        <div @click="sliderPaginationHandler('back')" class="slider-arrow cursor-pointer p-8.5 arrow-prev mr-2.5 transform rotate-180">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M10 17L17 10L10 3" stroke="white" stroke-width="2" stroke-linejoin="round"/>
            <path d="M2 10L17 10" stroke="white" stroke-width="2" stroke-linejoin="round"/>
          </svg>
        </div>
        <div @click="sliderPaginationHandler('forward')" class="slider-arrow cursor-pointer p-8.5 arrow-next">
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M10 17L17 10L10 3" stroke="white" stroke-width="2" stroke-linejoin="round"/>
            <path d="M2 10L17 10" stroke="white" stroke-width="2" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>
      <div class="numbers flex justify-end unselectable">
        <p class="current mr-2 text-3.55xl" style="line-height: 1;">{{mainSlide + 1}}</p>
        <div class="all flex flex-col">
          <p class="text-xxs mb-1" style="line-height: 1.6;">{{max}}</p>
          <div class="w-4 h-px" style="background:rgba(151, 163, 203, 0.6);;"></div>
        </div>
      </div>
    </div>
    <div class="right main-slider relative w-217.5 h-150  overflow-hidden">
      <transition :name="sliderDirection" v-for="(item, index) in text.images" :key="item + index">
        <img v-if="mainSlide === index" class="unselectable absolute left-0 w-217.5 h-150" :src="require('@/assets/images/' + src + '/01/slider/' + item + '.png')" alt="">
      </transition>
    </div>
  </div>
</template>

<script>
export default {
  name: "doubleSlider",
  props:['text', 'src'],
  computed:{
    max(){
      return this.text.images.length
    }
  },
  methods:{
    sliderPaginationHandler(direction){
      this.sliderDirection = direction
      if (direction === 'back'){
        this.mainSlide--
        this.additionalSlide--
      }
      if (direction === 'forward'){
        this.mainSlide++
        this.additionalSlide++
      }
      if (this.mainSlide === this.max){
        this.mainSlide = 0
      }
      if (this.additionalSlide === this.max){
        this.additionalSlide = 0
      }
      if (this.mainSlide === -1){
        this.mainSlide = this.max - 1
      }
      if (this.additionalSlide === -1){
        this.additionalSlide = this.max - 1
      }
    }
  },
  data(){
    return{
      sliderDirection:'forward',
      mainSlide:0,
      additionalSlide:3,
    }
  }
};
</script>

<style scoped lang="scss">
//Slider start
.forward-enter-active,
.forward-leave-active,
.back-enter-active,
.back-leave-active{
  transition: all linear .3s;
}
.forward-enter-from,
.back-leave-to{
  left: 100%;
}
.back-enter-from,
.forward-leave-to{
  left: -100%;
}
.slider-arrow{

  border: 1px solid ;
  border-color: #323749;
  transition: all linear .2s;
}
.slider-arrow:hover{
  border-color: white;
}
//Slider end
</style>