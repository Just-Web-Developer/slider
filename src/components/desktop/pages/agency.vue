<template>
  <div class="agency">
    <agencyWrappers :slide="slide" @nextSlide="$emit('nextSlide')" @nav="$emit('nav')" @goHome="$emit('goHome')"/>
    <div style="z-index: -1;position: absolute;width: 85.1875rem;height: 85.1875rem;left: -39.8125rem;top: calc(100vh + 6.125rem) ;background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 133, 255, 0) 100%);"></div>
    <div style="z-index: -1;position: absolute;width: 1122px;height: 1122px;left: 1389px;top: calc(100vh - 192px) ;background: radial-gradient(50% 50% at 50% 50%, rgba(255, 46, 83, 0.2) 0%, rgba(255, 46, 83, 0) 100%);"></div>
    <div style="z-index: -1;position: absolute;width: 1122px;height: 1122px;left: -351px;top: calc(300vh + 339px) ;background: radial-gradient(50% 50% at 50% 50%, rgba(255, 46, 83, 0.2) 0%, rgba(255, 46, 83, 0) 100%);"></div>
    <div style="position: absolute;width: 1122px;height: 1122px;left: -351px;top: calc(400vh - 561px);background: radial-gradient(50% 50% at 50% 50%, rgba(255, 46, 83, 0.2) 0%, rgba(255, 46, 83, 0) 100%);"></div>
    <agencySlide1/>
    <agencySlide2/>
    <agencySlide3/>
    <agencySlide4/>
    <agencySlide5 @contact="$emit('contact')"/>
  </div>

</template>

<script>
import agencyWrappers from "../agency/agencyWrappers";


import agencySlide1 from "../agency/agencySlide1";
import agencySlide2 from "../agency/agencySlide2";
import agencySlide3 from "../agency/agencySlide3";
import agencySlide4 from "../agency/agencySlide4";
import agencySlide5 from "../agency/agencySlide5";

export default {
  name: "Agency",
  props:['slide'],
  components:{
    agencySlide1,
    agencySlide2,
    agencySlide3,
    agencySlide4,
    agencySlide5,
    agencyWrappers
  },
  emits:['goHome', 'contact', 'nextSlide', 'nav']
};
</script>

<style scoped>
.agency > .slide{
  width: 100vw;
  height: 100vh;
}
</style>
