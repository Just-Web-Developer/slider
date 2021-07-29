<template>
  <slide1 />
  <div class="gradient">
    <div
      style="
          z-index: -10;
          position: absolute;
          width: 1122px;
          height: 1122px;
          left: -518px;
          top: 107px;
          background: radial-gradient(50% 50% at 50% 50%,rgba(0, 133, 255, 0.2) 0%,rgba(0, 133, 255, 0) 100%);
        "
    ></div>
    <div
      style="
          z-index: -10;
          position: absolute;
          width: 1122px;
          height: 1122px;
          left: -322px;
          top: 391px;
          background: radial-gradient(50% 50% at 50% 50%,rgba(242, 41, 89, 0.3) 0%,rgba(242, 41, 89, 0) 100%);
        "
    ></div>
    <div
      style="
          z-index: -10;
          position: absolute;
          width: 1122px;
          height: 1122px;
          left: 101px;
          top: 779px;
          background: radial-gradient(50% 50% at 50% 50%,rgba(0, 133, 255, 0.2) 0%,rgba(0, 128, 247, 0) 100%);
        "
    ></div>
  </div>
  <slide2 />
  <div class="gradient" :class="'grad-slide-'+windows.main.slide" id="grad-3-4"
       style="
        z-index: -10;
        transition: all linear .8s;
        position: absolute;
        width: 1122px;
        height: 1122px;
        left: 1200px;

        background: radial-gradient(50% 50% at 50% 50%,rgba(255, 46, 83, 0.3) 0%,rgba(255, 46, 83, 0) 100%);
      "
  ></div>
  <slide3 :clientSlide="windows.main.slide3.clientSlide" @contact="contactActive = true"  />
  <transition name="gradient">
    <div v-if="windows.main.slide === 3" class="gradient blue-grad-3"
         style="
        z-index: -10;
        width: 1122px;
        height: 1122px;
        background: radial-gradient(50% 50% at 50% 50%,rgba(0, 133, 255, 0.2) 0%,rgba(0, 133, 255, 0) 100%);
      "
    ></div>
  </transition>
  <slide4 />
  <slide5 />
  <div class="gradient blue-grad-5" :class="windows.main.slide > 5 ? 'unactive' : ''"
       style="z-index: -10; position: absolute;
          width: 1122px;
          height: 1122px;
          top: calc(400vh + 190px);
          background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 133, 255, 0) 100%);">
  </div>
  <slide6 />
  <div class="gradient" style="z-index: -10;position: absolute;
        width: 1122px;
        height: 1122px;
        left: 1330px;
        top: calc(500vh + 335px) ;
        background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 133, 255, 0) 100%);"></div>
  <slide7 @contact="$emit('contact')" />
</template>

<script>
import slide1 from "../slides/slide1";
import slide2 from "../slides/slide2";
import slide3 from "../slides/slide3";
import slide4 from "../slides/slide4";
import slide5 from "../slides/slide5";
import slide6 from "../slides/slide6";
import slide7 from "../slides/slide7";

export default {
  name: "Main",
  props:['windows'],
  emits:['contact'],
  components:{
    slide1,
    slide2,
    slide3,
    slide4,
    slide5,
    slide6,
    slide7
  }
};
</script>

<style scoped>

</style>