<template>
  <div  class="first-slide-animation" :class="{'mobile': mobile}">
    <div id="hud_1" class=" hud absolute" >
      <img  src="@/assets/images/slide_1/animation_hud/01.svg"  alt="">
    </div>
    <div id="hud_2" class=" hud absolute" >
      <img  src="@/assets/images/slide_1/animation_hud/02.svg"  alt="">
    </div>
    <div id="hud_3" class=" hud absolute" >
      <img  src="@/assets/images/slide_1/animation_hud/03.svg" alt="">
    </div>
    <video
      class="absolute w-125 xl:w-240 h-125 xl:h-auto right-0 top-0 first-slide-animation"
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
  name: "firstAnimation",
  props: {
    mobile:{
      type:Boolean,
      default:false
    }
  }
};
</script>

<style lang="scss" scoped>
  .first-slide-animation{
    div{
      position: absolute;
      right: 6.1875rem;
      top: 6.93375rem;
      img{
        width: 46.131875rem;
        height: 46.131875rem;
      }
    }
  }
  .first-slide-animation.mobile{
    div{
      position: absolute;
      left: 5vw;
      right: auto;
      top: 5rem;
      img{
        width: 90vw;
        height: 90vw;
      }
    }
  }

  #hud_1{
    animation:ease-out 7.103s infinite normal hud_1;
  }
  @keyframes hud_1{
    0%{
      transform: rotate(0deg);
    }
    25.34%{
      transform: rotate(0deg);
    }
    33.79%{
      transform: rotate(0deg);
    }
    33.8%{
      transform: rotate(0deg);
    }
    42.248%{
      transform: rotate(-90deg);
    }
    42.262%{
      transform: rotate(-90deg);
    }
    59.156%{
      transform: rotate(-240deg);
    }
    70.419%{
      transform: rotate(-240deg);
    }
    87.314%{
      transform: rotate(-330deg);
    }
    87.328%{
      transform: rotate(-330deg);
    }
    100%{
      transform: rotate(-360deg);
    }
  }
  #hud_2{
    animation:ease-out 7.103s infinite normal hud_2;
  }
  @keyframes hud_2{
    0%{
      transform: rotate(0deg);
    }
    25.34%{
      transform: rotate(0deg);
    }
    33.79%{
      transform: rotate(0deg);
    }
    33.8%{
      transform: rotate(0deg);
    }
    42.248%{
      transform: rotate(-90deg);
    }
    42.262%{
      transform: rotate(-90deg);
    }
    59.156%{
      transform: rotate(-90deg);
    }
    70.419%{
      transform: rotate(-90deg);
    }
    87.314%{
      transform: rotate(-210deg);
    }
    87.328%{
      transform: rotate(-210deg);
    }
    100%{
      transform: rotate(-360deg);
    }
  }
  #hud_3{
    animation:ease-out 7.103s infinite normal hud_3;
  }
  @keyframes hud_3{
    0%{
      transform: rotate(0deg);
    }
    25.34%{
      transform: rotate(0deg);
    }
    33.79%{
      transform: rotate(-156deg);
    }
    33.8%{
      transform: rotate(-156deg);
    }
    42.248%{
      transform: rotate(-246deg);
    }
    42.262%{
      transform: rotate(-246deg);
    }
    59.156%{
      transform: rotate(-246deg);
    }
    70.419%{
      transform: rotate(-246deg);
    }
    87.314%{
      transform: rotate(-360deg);
    }
    87.328%{
      transform: rotate(-360deg);
    }
    100%{
      transform: rotate(-360deg);
    }
  }

  //#hud_1 img{
  //  width: 2.167rem;
  //  height: 14.94925rem;
  //}
  //#hud_2 img{
  //  width: 4.5625rem;
  //  height: 2.875rem;
  //}
  //#hud_3 img{
  //  width: 0.3125rem;
  //  height: 0.3125rem;
  //}
  //#hud_4 img{
  //  width: 0.875rem;
  //  height: 4.75rem;
  //}
</style>
