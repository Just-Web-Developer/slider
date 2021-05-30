<template>
  <div  class="first-slide-animation">
    <div id="hud_1" class="flex justify-end items-center  hud relative" style="transform: rotate(11deg)" >
      <img  src="../assets/images/slide_1/animation_hud/1.svg" class="absolute" style="transform: rotate(-1.3deg); width: 5.5%;" alt="">
    </div>
    <div id="hud_2" class="flex justify-end items-center  hud absolute" style="transform: rotate(56deg)" >
      <img  src="../assets/images/slide_1/animation_hud/2.svg" style="transform: rotate(-71.8deg);position: relative;right: -29px; " alt="">
    </div>
    <div id="hud_3" class="flex justify-end items-center  hud absolute" style="transform: rotate(45deg)" >
      <img src="../assets/images/slide_1/animation_hud/3.svg" style="position: relative;right: 2px;transform: rotate(-58deg);" alt="">
    </div>
    <div id="hud_4" class="flex justify-end items-center  hud absolute" style="transform: rotate(-118deg)">
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
      transform: rotate(11deg);
    }
    15%{
      transform: rotate(11deg);
    }
    35%{
      transform: rotate(11deg);
    }
    40%{
      transform: rotate(-70deg);
    }
    55%{
      transform: rotate(-70deg);
    }
    60%{
      transform: rotate(-220deg);
    }
    75%{
      transform: rotate(-220deg);
    }
    80%{
      transform: rotate(-300deg);
    }
    95%{
      transform: rotate(-300deg);
    }
    100%{
      transform: rotate(-349deg);
    }
  }
  #hud_2{
    animation:linear 7s infinite normal hud_2;
  }
  @keyframes hud_2{
    0%{
      transform: rotate(56deg);
    }
    15%{
      transform: rotate(56deg);
    }
    35%{
      transform: rotate(56deg);
    }
    40%{
      transform: rotate(-25deg);
    }
    55%{
      transform: rotate(-25deg);
    }
    75%{
      transform: rotate(-25deg);
    }
    80%{
      transform: rotate(-105deg);
    }
    95%{
      transform: rotate(-105deg);
    }

    100%{
      transform: rotate(-304deg);
    }
  }
  #hud_3{
    animation:linear 7s infinite normal hud_3;
  }
  @keyframes hud_3{
    0%{
      transform: rotate(45deg);
    }
    15%{
      transform: rotate(45deg);
    }
    35%{
      transform: rotate(45deg);
    }
    40%{
      transform: rotate(-36deg);
    }
    55%{
      transform: rotate(-36deg);
    }
    75%{
      transform: rotate(-36deg);
    }
    80%{
      transform: rotate(-116deg);
    }
    95%{
      transform: rotate(-116deg);
    }

    100%{
      transform: rotate(-315deg);
    }
  }
  #hud_4{
    animation:linear 7s infinite normal hud_4;
  }
  @keyframes hud_4{
    0%{
      transform: rotate(-118deg);
    }
    15%{
      transform: rotate(-118deg);
    }
    20%{
      transform: rotate(-282deg);
    }
    35%{
      transform: rotate(-282deg);
    }
    40%{
      transform: rotate(-363deg);
    }
    55%{
      transform: rotate(-363deg);
    }
    75%{
      transform: rotate(-363deg);
    }
    80%{
      transform: rotate(-443deg);
    }
    95%{
      transform: rotate(-443deg);
    }

    100%{
        transform: rotate(-478deg);
    }
  }

</style>
