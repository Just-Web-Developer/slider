<template>
  <div  class="first-slide-animation">
    <div id="hud_1" class="flex justify-end items-center  hud relative" style="transform: rotate(22deg)" >
      <img  src="../assets/images/slide_1/animation_hud/1.svg" class="absolute" style="transform: rotate(-1.4deg); width: 6%;" alt="">
    </div>
    <div id="hud_2" class="flex justify-end items-center  hud absolute" style="transform: rotate(71deg)" >
      <img  src="../assets/images/slide_1/animation_hud/2.svg" style="transform: rotate(-70deg);position: relative;right: -29px; " alt="">
    </div>
    <div id="hud_3" class="flex justify-end items-center  hud absolute" style="transform: rotate(60deg)" >
      <img src="../assets/images/slide_1/animation_hud/3.svg" style="position: relative;right: 2px;transform: rotate(-58deg);" alt="">
    </div>
    <div id="hud_4" class="flex justify-end items-center  hud absolute" style="transform: rotate(-115deg)">
      <img  src="../assets/images/slide_1/animation_hud/4.svg" style="transform: rotate(-7deg);" alt="">
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
  }

  #hud_1{
    animation:linear 7s infinite normal hud_1;
  }
  @keyframes hud_1{
    0%{
      transform: rotate(22deg);
    }
    15%{
      transform: rotate(22deg);
    }
    //1-2
    31%{
      transform: rotate(22deg);
    }
    42%{
      transform: rotate(-64deg);
    }
    47%{
      transform: rotate(-64deg);
    }
    58%{
      transform: rotate(-211deg);
    }
    73%{
      transform: rotate(-211deg);
    }
    84%{
      transform: rotate(-300deg);
    }
    89%{
      transform: rotate(-300deg);
    }
    100%{
      transform: rotate(-338deg);
    }
  }
  #hud_2{
    animation:linear 7s infinite normal hud_2;
  }
  @keyframes hud_2{
    0%{
      transform: rotate(71deg);
    }
    15%{
      transform: rotate(71deg);
    }
    31%{
      transform: rotate(71deg);
    }
    42%{
      transform: rotate(-15deg);
    }
    55%{
      transform: rotate(-15deg);
    }
    75%{
      transform: rotate(-15deg);
    }
    80%{
      transform: rotate(-125deg);
    }
    95%{
      transform: rotate(-125deg);
    }

    100%{
      transform: rotate(-289deg);
    }
  }
  #hud_3{
    animation:linear 7s infinite normal hud_3;
  }
  @keyframes hud_3{
    0%{
      transform: rotate(60deg);
    }
    15%{
      transform: rotate(60deg);
    }
    35%{
      transform: rotate(60deg);
    }
    40%{
      transform: rotate(-26deg);
    }
    55%{
      transform: rotate(-26deg);
    }
    75%{
      transform: rotate(-26deg);
    }
    80%{
      transform: rotate(-136deg);
    }
    95%{
      transform: rotate(-136deg);
    }

    100%{
      transform: rotate(-300deg);
    }
  }
  #hud_4{
    animation:linear 7s infinite normal hud_4;
  }
  @keyframes hud_4{
    0%{
      transform: rotate(-115deg);
    }
    15%{
      transform: rotate(-115deg);
    }
    20%{
      transform: rotate(-267deg);
    }
    35%{
      transform: rotate(-267deg);
    }
    40%{
      transform: rotate(-353deg);
    }
    55%{
      transform: rotate(-353deg);
    }
    75%{
      transform: rotate(-353deg);
    }
    80%{
      transform: rotate(-463deg);
    }
    95%{
      transform: rotate(-463deg);
    }
    100%{
        transform: rotate(-475deg);
    }
  }

</style>
