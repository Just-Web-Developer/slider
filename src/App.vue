<template>

  <div class="body overflow-hidden" :class="'slide-' + slide" @wheel="scrollingWheel($event)">
    <transition name="contacts">
      <contact @wheel.passive.stop v-if="contactActive" @closeContacts="contactActive = false"/>
    </transition>
    <FixWrapper
      @nextSlide="nextSlide()"
      @prevSlide="prevSlide()"
      @contact="contactActive = true"
      :state="slide"
      class="z-50"

    />
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
    <div class="gradient" :class="'grad-slide-'+slide" id="grad-3-4"
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
    <slide3 :clientSlide="slide3.clientSlide" />
    <transition name="gradient">
      <div v-if="slide === 3" class="gradient blue-grad-3"
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
    <div class="gradient blue-grad-5" :class="slide > 5 ? 'unactive' : ''"
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
    <slide7 />
  </div>
</template>

<script>
import FixWrapper from "@/components/FixWrapper";

import slide1 from "./slides/slide1";
import slide2 from "./slides/slide2";
import slide3 from "./slides/slide3";
import slide4 from "./slides/slide4";
import slide5 from "./slides/slide5";
import slide6 from "./slides/slide6";
import slide7 from "./slides/slide7";
import contact from "./components/contact";

export default {
  name: "App",
  components: {
    FixWrapper,
    slide1,
    slide2,
    slide3,
    slide4,
    slide5,
    slide6,
    slide7,
    contact
  },
  data() {
    return {
      slide: 1,
      max: 7,
      slide3: {
        clientSlide: 1,
      },
      scrolling:false,
      contactActive:false
    };
  },
  methods: {
    nextSlide() {
      if (this.scrolling){
        return;
      }
      this.scrolling = true
      if (this.slide === 3 && this.slide3.clientSlide === 1) {

        this.slide3.clientSlide = 2;
        setTimeout(() => this.scrolling = false, 800)
        return;
      }
      if (this.slide < this.max) {
        this.slide++;
      }
      else {
        this.slide = 1;
      }
      setTimeout(() => this.scrolling = false, 800)
    },
    prevSlide() {
      if (this.scrolling){
        return;
      }
      this.scrolling = true
      if (this.slide === 3 && this.slide3.clientSlide === 2) {
        this.slide3.clientSlide = 1;
        setTimeout(() => this.scrolling = false, 800)
        return;
      }
      if (this.slide !== 1) {
        this.scrolling = true
        this.slide--;
        setTimeout(() => this.scrolling = false, 800)
      }
    },
    scrollingWheel(e){
      if (e.deltaY > 0){this.nextSlide()}
      if (e.deltaY < 0){this.prevSlide()}
    }
  },
};
</script>

<style lang="scss">
#app {
  height: 100vh;
}
.body {
  font-family: "Montserrat", sans-serif;
  color: white;
  position: relative;
  transition: all linear .8s;
  top: 0;
  bottom: 0;
}
.body.slide-1 {
  margin-top: 0;
  height: 100vh;
}
.body.slide-2 {
  margin-top: -100vh;
  height: 200vh;
}
.body.slide-3 {
  margin-top: -200vh;
  height: 300vh;
}
.body.slide-4 {
  margin-top: -300vh;
  height: 400vh;
}
.body.slide-5 {
  margin-top: -400vh;
  height: 500vh;
}
.body.slide-6 {
  margin-top: -500vh;
  height: 600vh;
}
.body.slide-7 {
  margin-top: -600vh;
  height: 700vh;
}

.grad-slide-2,.grad-slide-3{
  top: calc(100vh + 504px);
}
.grad-slide-4,.grad-slide-5{
  top: calc(200vh + 504px);
}

.blue-grad-5{
  transition: all linear .8s;
  left: -495px;
}
.blue-grad-5.unactive{
  transition: all linear .8s;
  left: -100%;
}

.client:hover {
  background: rgba(255, 46, 83, 1);
  img {
    transform: scale(1.3);
  }
}
.pagination {
  transition: all linear 0.8s;
}
.pagination.active {
  background: rgba(255, 46, 83, 1);
}

.blue-grad-3{
  left: -266px;
  top: calc(200vh + 225px);
  position: absolute;
}

.client-1-enter-active,
.client-1-leave-active,
.client-2-enter-active,
.client-2-leave-active{
  transition: all 0.8s linear;
}

.gradient-enter-active,
.gradient-leave-active{
  transition: left linear .8s;
}

.gradient-enter-from,
.gradient-leave-to{
  top: 225px;
  position: fixed;
  left: 100vw;
}


.client-1-enter-from,
.client-1-leave-to {
  opacity: 0;
  transform: translateX(-100%);
}
.client-2-enter-from,
.client-2-leave-to {
  opacity: 0;
  transform: translateX(100%);
}
.become-client {
  p,
  .plus,
  .plus div {
    transition: all 0.2s linear;
  }
  .plus {
    background: #ff2e53;
    div {
      background: white;
    }
  }
  .connect-grad {
    left: -11rem;
    top: -3rem;
    div {
      border-radius: 50%;
      transform: scale(0);
      transition: all 0.15s linear;
    }
    #grad-1 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 66px;
      top: -90px;

      background: linear-gradient(
        321.88deg,
        rgba(7, 25, 61, 0) 12.53%,
        #f22959 43.45%,
        #ff0000 60.5%
      );
      filter: blur(60px);
    }
    #grad-2 {
      position: absolute;
      width: 112.05px;
      height: 112.05px;
      left: 203.59px;
      top: -86.41px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(209.3deg, #7b61ff -2.55%, #7b61ff 64.59%);
      filter: blur(60px);
    }
    #grad-3 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 136.28px;
      top: -21.72px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(
        209.3deg,
        rgba(242, 137, 41, 0) -2.55%,
        #f22959 64.59%
      );
      opacity: 0.7;
      filter: blur(60px);
    }
  }
  .connect-content:hover {
    p {
    }
    .plus {
      transform: rotate(180deg);
      background: white;
      margin-right: 3rem;
      div {
        background: black;
      }
    }
  }
  .connect-content:hover + .connect-grad {
    div {
      transform: scale(1);
    }
    #grad-2 {
      transform: rotate(165deg) scale(1);
    }
    #grad-3 {
      transform: rotate(165deg) scale(1);
    }
  }
}

.contacts-enter-active,
.contacts-leave-active{
  transition:all .3s linear ;
}
.contacts-enter-to,
.contacts-leave-from{
  left: 0;
}
.contacts-enter-from,
.contacts-leave-to{
  left: 100vw;
}
</style>
