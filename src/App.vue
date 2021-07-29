<template>

  <div class="body overflow-hidden" :class="'slide-' + windows[content].slide" @wheel="scrollingWheel($event)">
    <transition name="contacts">
      <contact @wheel.passive.stop class="contact" :slide="windows[content].slide" v-if="contactActive" @closeContacts="contactActive = false"/>
    </transition>
    <transition name="menu">
      <Menu
        @wheel.passive.stop
        class="menu"
        :slide="windows[content].slide"
        :language="lang"
        v-if="menuActive"
        @closeContacts="menuActive = false"
        @setNavRoute="setRoute($event)"
        @setLang="lang = $event"
      />
    </transition>
    <FixWrapper
      @nextSlide="nextSlide()"
      @prevSlide="prevSlide()"
      @contact="contactActive = true"
      @openMenu="menuActive = !menuActive"
      :state="windows.main.slide"
      :menu="menuActive"
      :main="content === 'main'"
      class="z-50"

    />



    <Main v-if="content === 'main'" @contact="contactActive = true" :windows="windows"/>
    <Agency v-if="content === 'agency'" @nextSlide="nextSlide()" :slide="windows.agency.slide" @contact="contactActive = true" @goHome="menuActive = !menuActive" />
  </div>
</template>

<script>
import FixWrapper from "@/components/FixWrapper";
import Main from "./components/main";
import Agency from "./components/agency";

import contact from "./components/contact";
import Menu from "./components/menu"

export default {
  name: "App",
  components: {
    FixWrapper,
    Main,
    contact,
    Menu,
    Agency
  },
  data() {
    return {
      content:'main',
      lang: 'ru',
      windows:{
        main:{
          slide: 1,
          max: 7,
          slide3: {
            clientSlide: 1,
          },
        },
        agency:{
          slide: 1,
          max: 5,
        },
        projects:{
          slide: 1,
          max: 7,
        },
        blog:{
          slide: 1,
          max: 7,
        },
        contacts:{
          slide: 1,
          max: 7,
        },
      },
      scrolling:false,
      contactActive:false,
      menuActive: false
    };
  },
  methods: {
    nextSlide() {
      if (this.scrolling){
        return;
      }
      this.scrolling = true
      if (this.windows.main.slide === 3 && this.windows.main.slide3.clientSlide === 1) {

        this.windows.main.slide3.clientSlide = 2;
        setTimeout(() => this.scrolling = false, 800)
        return;
      }
      if (this.windows[this.content].slide < this.windows[this.content].max) {
        this.windows[this.content].slide++;
      }
      else {
        this.windows[this.content].slide = 1;
      }
      setTimeout(() => this.scrolling = false, 800)
    },
    prevSlide() {
      if (this.scrolling){
        return;
      }
      this.scrolling = true
      if (this.windows.main.slide === 3 && this.windows.main.slide3.clientSlide === 2) {
        this.windows.main.slide3.clientSlide = 1;
        setTimeout(() => this.scrolling = false, 800)
        return;
      }
      if (this.windows[this.content].slide !== 1) {
        this.scrolling = true
        this.windows[this.content].slide--;
        setTimeout(() => this.scrolling = false, 800)
      }
    },
    scrollingWheel(e){
      if (e.deltaY > 0){this.nextSlide()}
      if (e.deltaY < 0){this.prevSlide()}
    },
    setRoute(e){
      this.content = e
      if (this.content === 'main'){
        return
      }
      this.menuActive = false
    }
  },
};
</script>

<style lang="scss">
#app {
  height: 100vh;
}
.body, .main {
  font-family: "Montserrat", sans-serif;
  color: white;
  position: relative;
  transition: all linear .8s;
  top: 0;
  bottom: 0;
}
.body.slide-1{
  margin-top: 0;
  height: 100vh;
}
.body.slide-2{
  margin-top: -100vh;
  height: 200vh;
}
.body.slide-3{
  margin-top: -200vh;
  height: 300vh;
}
.body.slide-4{
  margin-top: -300vh;
  height: 400vh;
}
.body.slide-5{
  margin-top: -400vh;
  height: 500vh;
}
.body.slide-6{
  margin-top: -500vh;
  height: 600vh;
}
.body.slide-7{
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
