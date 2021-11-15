<template>
  <p class="text-red-700">{{touch.start}}</p>
  <p class="text-yellow-600">{{touch.current}}</p>
  <p class="text-green-600">{{touch.end}}</p>
  <p class="text-coral-700">{{touch.sum}}</p>
  <p class="text-blue-700">{{choosedPoint}}</p>
  <div id="mobile-slider" class="slider ml-4.5 flex w-max max-w-none left-0 relative min-h-42.5 mb-40" :style="'left:' + swipe + 'px' ">
    <div ref="slide" class="slider-slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slider-slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slider-slide mr-7.5 w-62.5 flex flex-col">
      <img src="@/assets/images/slide_2/stack/enter.svg"
           class="h-19 w-19 p-4.5 rounded-full mb-5"
           style="background: rgba(110, 117, 141, 0.2)"
           alt="" />
      <p class="fz-16 font-medium" style="line-height: 1.5625rem">Cистема входа, учета сотрудников по заданным параметрам</p>
    </div>
    <div class="slider-slide w-62.5 flex flex-col">
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
      swiping: false,
      swiped: false,
      touch:{
        start:0,
        prevStart:0,
        current:0,
        prevCurrent:0,
        end:0,
        prevEnd:0,
        sum:0,
      },
      choosedPoint: null,
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
      this.touch["prev" + e] = this.touch[e.toLowerCase()];
    },
    started(data){
      this.touch.start = data
      this.swiping = true
      this.choosedPoint = null
    },
    moving(data){
      this.touch.current = data
    },
    finished(data){
      this.swiping=false
      this.touch.end = data
      this.setControl()
    },
    setSwipe(){
      if (this.swiping){
        return this.swipingFunc()
      }
      return this.finishSwipe()

    },
    swipingFunc(){
      if (this.touch.current === 0 ){
        return this.touch.sum
      }
      return this.touch.current - this.touch.start + this.touch.sum
    },
    finishSwipe(){
      this.touch.sum += this.touch.end - this.touch.start
      if (this.touch.start !== 0 || this.touch.current !== 0 || this.touch.end !== 0){
        this.swiped = true
      }
      this.touch.start = this.touch.current = this.touch.end = 0

      return this.touch.sum
    },
    setControl(){
      this.controlPoints.forEach((item, index)=>{
        if (this.touch.sum < item && index === 0){
          this.choosedPoint = item
          this.aiming()
          return;
        }
        if (this.touch.sum > item && (index + 1) === this.controlPoints.length){
          this.choosedPoint = item
          this.aiming()
          return;
        }
        if (item > this.touch.sum && this.touch.sum > this.controlPoints[index-1]){
          let mid = (item + this.controlPoints[index-1]) / 2
          if (mid > this.touch.sum){
            this.choosedPoint = this.controlPoints[index-1]
            this.aiming()
            return;
          }
          else {
            this.choosedPoint = item
            this.aiming()
          }
        }
      })
    },
    aiming(){
      let duration = 100 // duration of aiming in milliseconds
      let initial = this.touch.sum
      if (this.touch.sum >= this.choosedPoint){
        let interval = setInterval(()=>{
          this.touch.sum -= Math.abs(this.choosedPoint - initial) / duration
          if (Math.abs(this.touch.sum - this.choosedPoint) < (window.innerWidth / 200)){
            clearInterval(interval)
          }
        }, 1)
      }
      else if(this.touch.sum < this.choosedPoint){
        let interval = setInterval(()=>{
          this.touch.sum += Math.abs(this.choosedPoint - initial) / duration
          if (Math.abs(this.touch.sum - this.choosedPoint) < (window.innerWidth / 200)){
            clearInterval(interval)
          }
        }, 1)
      }
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


    let slides = document.querySelectorAll(".slider-slide");
    let slideStyles = window.getComputedStyle(slides[0])
    this.slideSize = parseFloat(slideStyles.width) + parseFloat(slideStyles.marginRight)
    for (let p = 0; p < slides.length; p++) {
      this.controlPoints.unshift(this.slideSize * p * -1)
    }
  }
};
</script>

<style scoped>

</style>