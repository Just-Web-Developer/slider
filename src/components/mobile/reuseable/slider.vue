<template>
  <p class="text-red-700">{{touch.start}}</p>
  <p class="text-yellow-600">{{touch.current}}</p>
  <p class="text-green-600">{{touch.end}}</p>
  <div id="mobile-slider" class="slider ml-4.5 flex w-max max-w-none left-0 relative min-h-42.5 mb-40" :style="'left:' + swipe + 'px' ">
    <div ref="slide" class="slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slide w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "slider",
  data(){
    return{
      swiping:false,
      touch:{
        start:0,
        prevStart:0,
        current:0,
        prevCurrent:0,
        end:0,
        prevEnd:0,
        sum:0
      },
      slideSize:0,
      controlPoints:[]
    }
  },
  computed:{
    swipe(){
      return this.setSwipe()
    }
  },
  methods:{
    setPrev(e){
      this.touch['prev' + e] = this.touch[e.toLowerCase()]
    },
    started(data){
      this.touch.start = data
      this.swiping=true
    },
    moving(data){
      this.touch.current = data
    },
    finished(data){
      this.swiping=false
      this.touch.end = data

    },
    setSwipe(){
      if (this.swiping){
        return this.swipingFunc()
      }
      return this.finishSwipe()
    },
    swipingFunc(){
      if (this.touch.current === 0 || this.touch.current === this.touch.prevCurrent ){
        return this.touch.sum
      }
      this.setPrev('Current')
      let res = (this.touch.current - this.touch.start)
      return res
    },
    finishSwipe(){
      this.touch.sum += this.touch.end - this.touch.start
      return this.touch.sum
    }
  },
  mounted: function () {
    document.getElementById('mobile-slider').addEventListener('touchstart', (event) => {
      this.started(event.changedTouches[0].clientX);
    })
    document.getElementById('mobile-slider').addEventListener('touchmove', (event) => {
      this.moving(event.changedTouches[0].clientX);
    })
    document.getElementById('mobile-slider').addEventListener('touchend', (event) => {
      this.finished(event.changedTouches[0].clientX)
    })


    let slides = document.querySelectorAll('.slide')
    let slideStyles = window.getComputedStyle(slides[0])
    this.slideSize = parseFloat(slideStyles.width) + parseFloat(slideStyles.marginRight)
    for (let p = 0; p < slides.length; p++) {
      this.controlPoints.push(this.slideSize * p)
    }
  }
};
</script>

<style scoped>

</style>