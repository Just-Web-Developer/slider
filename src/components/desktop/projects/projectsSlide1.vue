<template>
  <div class="pt-40 pl-46.25 flex slide">
    <video
      autoplay
      loop
      muted
      class="w-151.5 h-151.5 mr-15"
      src="@/assets/videos/projects.mp4" alt=""></video>
    <div class="content mt-40 flex flex-col w-184.75">
      <div class="header flex justify-between">
        <p class="fz-202" style="color: rgba(50, 55, 73, 1)">/ {{ text.projects }}</p>
        <img class="h-10 w-10" src="@/assets/images/box.svg" alt="">
      </div>
      <p class="mt-25 text-justify fz-201 font-medium" style="text-indent: 15rem">{{ text.bigExp }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "projectsSlide1",
  props:['lang'],
  computed:{
    text(){
      return require("@/assets/text/projects/slide1/ru.json")
    }
  }
};
</script>

<style scoped>

</style>