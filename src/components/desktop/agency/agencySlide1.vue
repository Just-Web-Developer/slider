<template>
  <div class="pt-40 pl-46.25 flex slide">
    <video
      autoplay
      loop
      muted
      class="w-151.5 h-151.5 mr-15"
      src="@/assets/videos/agency.mp4" alt=""></video>
    <div class="content mt-10 flex flex-col w-184.75">
      <div class="header flex justify-between">
        <p class="text-1xxl" style="color: rgba(50, 55, 73, 1)">/ {{ text.AGENCY }}</p>
        <img class="h-full" src="@/assets/images/slide_2/about/team.svg" alt="">
      </div>
      <div class="us my-25 flex justify-between items-stretch">
        <div class="left w-55 mr-10 border-t border-b py-7.5" style="border-color: rgba(151, 163, 203, 0.3);">
          <p class="text-xxsm font-medium uppercase my-7.5" style="color: rgba(255, 46, 83, 1)">{{ text.we }}</p>
          <p class="font-medium text-xxl">{{ text.team }}</p>
        </div>
        <div class="right w-120 border-t border-b py-7.5" style="border-color: rgba(151, 163, 203, 0.3);" >
          <p class="text-xxsm font-medium uppercase my-7.5" style="color: rgba(255, 46, 83, 1)">{{ text.task[0] }}:</p>
          <p class="font-medium text-xxl pr-20">{{ text.task[1] }}</p>
        </div>
      </div>
      <p class="text-lg text-justify" style="color:rgba(192, 197, 216, 1)">{{ text.text }}
        <a class="underline" href="">{{ text.link }}</a></p>
    </div>
  </div>
</template>

<script>
export default {
  name: "agencySlide1",
  computed:{
    text(){
      return require("@/assets/text/agency/slide1/ru.json")
    }
  }
};
</script>

<style scoped>

</style>