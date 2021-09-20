<template>
  <div  class="first-slide-animation">
    <div id="hud_1" class="flex justify-end items-center  hud relative" style="transform: rotate(22deg)" >
      <img  src="@/assets/images/slide_1/animation_hud/1.svg" class="absolute" style="transform: rotate(-1.4deg); width: 6%;" alt="">
    </div>
    <div id="hud_2" class="flex justify-end items-center  hud absolute" style="transform: rotate(71deg)" >
      <img  src="@/assets/images/slide_1/animation_hud/2.svg" style="transform: rotate(-70deg);position: relative;right: -29px; " alt="">
    </div>
    <div id="hud_3" class="flex justify-end items-center  hud absolute" style="transform: rotate(60deg)" >
      <img src="@/assets/images/slide_1/animation_hud/3.svg" style="position: relative;right: 2px;transform: rotate(-58deg);" alt="">
    </div>
    <div id="hud_4" class="flex justify-end items-center  hud absolute" style="transform: rotate(-115deg)">
      <img  src="@/assets/images/slide_1/animation_hud/4.svg" style="transform: rotate(-7deg);" alt="">
    </div>
    <video
      class="absolute w-240 right-0 top-0 first-slide-animation"
      style="z-index: -10"
      autoplay
      loop
      muted
      src="@/assets/videos/slide_1.mp4"
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
  }

  #hud_1{
    transform: rotate(27deg);
    animation:ease-out 7.103s infinite normal hud_1;
  }
  @keyframes hud_1{
    0%{
      transform: rotate(27deg);
    }
    25.34%{
      transform: rotate(27deg);
    }
    33.79%{
      transform: rotate(27deg);
    }
    33.8%{
      transform: rotate(27deg);
    }
    42.248%{
      transform: rotate(-63deg);
    }
    42.262%{
      transform: rotate(-63deg);
    }
    59.156%{
      transform: rotate(-213deg);
    }
    70.419%{
      transform: rotate(-213deg);
    }
    87.314%{
      transform: rotate(-303deg);
    }
    87.328%{
      transform: rotate(-303deg);
    }
    99.9%{
      transform: rotate(-333deg);
    }
    100%{
      transform: rotate(27deg);
    }
  }
  #hud_2{
    transform: rotate(71deg);
    animation:ease-out 7.103s infinite normal hud_2;
  }
  @keyframes hud_2{
    0%{
      transform: rotate(71deg);
    }
    25.34%{
      transform: rotate(71deg);
    }
    33.79%{
      transform: rotate(71deg);
    }
    33.8%{
      transform: rotate(71deg);
    }
    42.248%{
      transform: rotate(-19deg);
    }
    42.262%{
      transform: rotate(-19deg);
    }
    59.156%{
      transform: rotate(-19deg);
    }
    70.419%{
      transform: rotate(-19deg);
    }
    87.314%{
      transform: rotate(-139deg);
    }
    87.328%{
      transform: rotate(-139deg);
    }
    99.9%{
      transform: rotate(-289deg);
    }
    100%{
      transform: rotate(71deg);
    }
  }
  #hud_3{
    transform: rotate(60deg);
    animation:ease-out 7.103s infinite normal hud_3;
  }
  @keyframes hud_3{
    0%{
      transform: rotate(60deg);
    }
    25.34%{
      transform: rotate(60deg);
    }
    33.79%{
      transform: rotate(60deg);
    }
    33.8%{
      transform: rotate(60deg);
    }
    42.248%{
      transform: rotate(-30deg);
    }
    42.262%{
      transform: rotate(-30deg);
    }
    59.156%{
      transform: rotate(-30deg);
    }
    70.419%{
      transform: rotate(-30deg);
    }
    87.314%{
      transform: rotate(-150deg);
    }
    87.328%{
      transform: rotate(-150deg);
    }
    99.9%{
      transform: rotate(-300deg);
    }
    100%{
      transform: rotate(60deg);
    }
  }
  #hud_4{
    transform: rotate(-115deg);
    animation:ease-out 7.103s infinite normal hud_4;
  }
  @keyframes hud_4{
    0%{
      transform: rotate(-112deg);
    }
    25.34%{
      transform: rotate(-112deg);
    }
    33.79%{
      transform: rotate(-268deg);
    }
    33.8%{
      transform: rotate(-268deg);
    }
    42.248%{
      transform: rotate(-358deg);
    }
    42.262%{
      transform: rotate(-358deg);
    }
    59.156%{
      transform: rotate(-358deg);
    }
    70.419%{
      transform: rotate(-358deg);
    }
    87.314%{
      transform: rotate(-472deg);
    }
    87.328%{
      transform: rotate(-472deg);
    }
    99.99%{
      transform: rotate(-472deg);
    }
    100%{
      transform: rotate(-112deg);
    }
  }

</style>
