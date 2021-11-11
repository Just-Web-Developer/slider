<template>
  <p class="text-red-700">{{touch.start}}</p>
  <p class="text-yellow-600">{{touch.current}}</p>
  <p class="text-green-600">{{touch.end}}</p>
  <div id="mobile-slider" class="slider ml-4.5 flex w-max max-w-none left-0 relative min-h-42.5 mb-40" :style="'left:' + swipe + 'px' ">
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
      touch:{
        start:0,
        prevStart:0,
        current:0,
        prevCurrent:0,
        end:0,
        prevEnd:0,
        cancel:0
      }
    }
  },
  computed:{
    swipe(){
      if (this.touch.current === 0 || this.touch.current === this.touch.prevCurrent ){
        return 0
      }
      this.setPrev('Current')
      let res = (this.touch.current - this.touch.start)
      console.log(res)
      return res
    }
  },
  methods:{
    setPrev(e){
      this.touch['prev' + e] = this.touch[e.toLowerCase()]
    }
  },
  mounted() {
    document.getElementById('mobile-slider').addEventListener('touchstart', (event)=>{
      this.touch.start = event.changedTouches[0].clientX
      console.log(event.changedTouches[0].clientX)
    })
    document.getElementById('mobile-slider').addEventListener('touchmove', (event)=>{
      this.touch.current = event.changedTouches[0].clientX
    })
    document.getElementById('mobile-slider').addEventListener('touchend', (event)=>{
      this.touch.end = event.changedTouches[0].clientX
    })
    document.getElementById('mobile-slider').addEventListener('touchcancel', (event)=>{
      this.touch.cancel = event.changedTouches[0].clientX
    })
  }
};
</script>

<style scoped>

</style>