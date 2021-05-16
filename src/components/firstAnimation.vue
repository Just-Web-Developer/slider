<template>
  <div  class="first-slide-animation">
    <div id="hud_1" class="flex justify-end items-center  hud relative" style="transform: rotate(45deg)" >
      <img  src="../assets/images/animation_hud/1.svg" class="absolute" style="transform: rotate(-1deg); width: 5.5%;" alt="">
    </div>
    <div id="hud_2" class="flex justify-end items-center  hud absolute" >
      <img  src="../assets/images/animation_hud/2.svg" style="transform: rotate(-70deg);position: relative;right: -29px; " alt="">
    </div>
    <div id="hud_3" class="flex justify-end items-center  hud absolute" >
      <img src="../assets/images/animation_hud/3.svg" style="position: relative;right: 2px;transform: rotate(-58deg);" alt="">
    </div>
    <div id="hud_4" class="flex justify-end items-center  hud absolute" >
      <img  src="../assets/images/animation_hud/4.svg" style="transform: rotate(-7deg);" alt="">
    </div>
    <video
      class="absolute w-240 right-0 top-0 first-slide-animation"
      style="z-index: -10"
      autoplay
      loop
      muted
      src="../assets/videos/1_slide.mp4"
    ></video>
  </div>
</template>

<script>
export default {
  name: "firstAnimation"
};
</script>

<style lang="scss" scoped>
  .first-slide-animation{
    div{
      position: absolute;
      width: 578.11px;
      height: 578.11px;
      right: 179px;
      top: 190.94px;
    }
    animation:linear 7s infinite normal hud;
  }
  @keyframes hud{
    0%{
      #hud_4{
        transform: rotate(-118deg);
      }
    }
    100%{
      #hud_4{
        transform: rotate(-478deg);
      }
    }
  }

</style>
