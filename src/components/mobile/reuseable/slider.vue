<template>
  <div id="mobile-slider" @mousemove="move($event)" class="slider ml-4.5 flex w-max max-w-none left-0 relative min-h-42.5 mb-40">
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
  methods:{
    start(e){
      console.log(e);
    },
    move(e){
      console.log(e);
    },
    end(){
      console.log();
    },
  }
};
</script>

<style scoped>

</style>