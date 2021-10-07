<template>
  <WrapGrads :agency="agency" :state="state" />
  <div class="slider-wrapper-top fixed flex left-18 right-18 top-11" style="z-index: 201;">
    <div class="menu cursor-pointer w-12.5" :class="{'unactive': !menu}" @click="$emit('openMenu')">
      <div class="menu-content">
        <transition name="menu-label" mode="out-in">
          <p v-if="!menu" class="uppercase font-medium text-xs mb-3">{{ text.menu }}</p>
          <p v-else class="uppercase font-medium text-xs mb-3">{{ text.close }}</p>
        </transition>

        <div class="h-5 relative w-full">
          <div
            class="absolute  h-2px  bg-white " :class="{'active-menu w-5 left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-45': menu, 'w-full top-0 left-0': !menu}"
          ></div>
          <div
            id="second-menu-strip"
            class="absolute  h-2px bg-white " :class="{'active-menu w-5 left-1/2 bottom-1/2 transform -translate-x-1/2 translate-y-1/2 -rotate-45': menu, 'w-1/2 bottom-0 left-0': !menu}"
          ></div>
        </div>
      </div>
      <div class="menu-grad relative -top-32 left-0" style="z-index: -1">
        <div class="blue-b"></div>
        <div class="blue-s"></div>
        <div class="purple"></div>
        <div class="purple-s"></div>
      </div>
    </div>


    <div class="max-frai ml-52.5 relative z-70" :class="{'cursor-pointer' : menu}" @click="$emit('setNavRoute', 'main')">
      <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
      <p
        class="uppercase inter font-bold mt-4 text-xxs"
        style="color: #ff2e53; letter-spacing: 1rem; line-height: 1"
      >
        {{ text.AGENCY }}
      </p>
    </div>
    <div class="ml-27 h-full mt-auto">
      <div class="h-8px w-px" style="background: #ff2e53"></div>
    </div>
    <div class="ml-65 agency  relative z-70">
      <p class="font-medium text-base" @mouseover="agencyGradsOn" @mouseleave="agencyGradsOff">
        {{ text.agency[0] }} <br />
        {{ text.agency[1] }}
      </p>
    </div>
    <div @click="$emit('contact')" class="connect ml-auto cursor-pointer relative z-70">
      <div class="connect-content flex justify-end items-center  ">
        <p class="uppercase font-semibold text-xsm mr-4">{{ text.contact }}</p>
        <div class="plus w-12.5 h-12.5 rounded-full relative">
          <div
            class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
          ></div>
          <div
            class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
          ></div>
        </div>
      </div>

      <div class="connect-grad relative" style="z-index: -1">
        <div id="grad-1"></div>
        <div id="grad-2"></div>
        <div id="grad-3"></div>
      </div>
    </div>
  </div>
  <div v-if="main" class="slider-wrapper-left fixed bottom-22 left-18 top-50">
    <div class="relative w-22.5 h-full states" :class="'state-'+state">
      <div id="first-strip"></div>
      <div id="second-strip"></div>
      <div id="third-strip"></div>
      <div id="fourth-strip"></div>
      <div id="fifth-strip"></div>
      <div id="sixth-strip"></div>
      <div id="seventh-strip"></div>
      <div class="absolute left-0 h-px w-1/3 opacity-30 bottom-0"></div>
    </div>
  </div>
  <div v-if="main" class="slider-wrapper-right fixed bottom-18 right-18 top-50 z-50">
    <div class="relative w-22.5 h-full">
      <div
        class="absolute right-0 transition-all h-px w-1/3 opacity-30 top-1.5"
      ></div>
      <div
        class="absolute right-0 transition-all h-3px w-1/6 opacity-60"
        style="top: 41.35%"
      ></div>
      <div
        class="absolute right-0 transition-all h-3px w-1/15 opacity-30"
        style="top: 43.695%"
      ></div>
      <div
        @click="$emit('prevSlide')"
        class="absolute flex bottom-2.5 right-0 cursor-pointer"
        style="background: transparent"
      >
        <div class="numbers flex mr-2 relative w-5 ">
          <transition name="numbers" v-for="item in 6" :key="item" >
            <p v-if="state === item" class="text-3xl absolute" style="line-height: 0.78; background:transparent;">{{item}}</p>
          </transition>
            <p class="text-3xl absolute first7 left-0 " :class="state !== 7 ? 'inactive' : '' " style=" background:transparent;">7</p>
          <transition name="second7">
            <p v-if="state === 7" class="text-3xl absolute left-0 " style="line-height: 0.78; background:transparent;">7</p>
          </transition>

        </div>
        <div class="flex flex-col">
          <div>
            <p class="number text-xxs third7" :class="state !== 7 ? 'inactive' : ''">7</p>
          </div>
          <div
            class="h-px w-15px mt-1"
            style="background: rgba(151, 163, 203, 0.6)"
          ></div>
        </div>
      </div>
    </div>
  </div>
  <div v-if="main" class="slider-wrapper-bottom fixed bottom-18 transform transition cursor-pointer z-50" style="left: 44.8%" @click="$emit('nextSlide')">
    <svg width="14" class="transform transition duration-800" :class="state === 7 ? 'rotate-180' : ''" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
      <path d="M6.99998 0V12" stroke-linejoin="round"/>
    </svg>
    <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">{{ state !== 7 ? text.scroll : text.back }}</p>
  </div>
</template>

<script>
import WrapGrads from "./WrapGrads";

export default {
  name: "wrappers",
  components: { WrapGrads },
  props:['state', 'menu', 'main'],
  data() {
    return {
      menuHover: null,
      agency: false
    };
  },
  emits:['prevSlide', 'nextSlide', 'contact', 'openMenu', 'setNavRoute'],
  methods:{
    agencyGradsOn(){
      this.agency = true
    },
    agencyGradsOff(){
      if(this.state === 7 ){
        return
      }
      this.agency = false
    }
  },
  watch:{
    state(){
      if (this.state === 7){
        this.agency = true
      }
      else{
        this.agency = false
      }
    }
  },
  computed:{
    text(){
      return require("@/assets/text/fixWrappers/ru.json")
    }
  }
};
</script>

<style lang="scss" scoped>
.slider-wrapper-left {
  .states {
    div {
      position: absolute;
      left: 0;
      background: #97a3cb;
    }
  }
  .state-1 {
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 0;
    }
    #second-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 10.41055805%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 33.5777126%;
    }
    #fourth-strip {
      height: 1px;
      width: 22.222%;
      opacity: 0.3;
      top: 37.683284%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 41.4956027%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 44.8680351%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 48.2404692%;
    }
  }
  .state-2{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 0;
    }
    #second-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 15.78%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 29.55%;
    }
    #fourth-strip {
      height: 1px;
      width: 22.222%;
      opacity: 0.3;
      top: 42.46%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 46.19%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 49.49%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 53.75%;
    }
  }
  .state-3{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 0;
    }
    #second-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 18.115%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 48.225%;
    }
    #fourth-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 57.77%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 59.975%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 67.93%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 69.52%;
    }
  }
  .state-4{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 0;
    }
    #second-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 10.57%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 75.4%;
    }
    #fourth-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 76.99%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 78.34%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 79.93%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 81.52%;
    }
  }
  .state-5{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 0;
    }
    #second-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 16.129%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 47.067%;
    }
    #fourth-strip {
      height: 1px;
      width: 22.222%;
      opacity: 0.3;
      top: 51.173%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 76.392%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 81.231%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 86.070%;
    }
  }
  .state-6{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 100%;
      opacity: 0.3;
      top: 10.117%;
    }
    #second-strip {
      height: 1px;
      width: 33%;
      opacity: 0.3;
      top: 35.923%;
    }
    #third-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 60.85%;
    }
    #fourth-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 81.964%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 83.577%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 85.483%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 87.39%;
    }
  }
  .state-7{
    div{
      transition: all .8s linear;
    }
    #first-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 0%;
    }
    #second-strip {
      height: 1px;
      width: 27.777%;
      opacity: 0.3;
      top: 2.639%;
    }
    #third-strip {
      height: 3px;
      width: 49.999%;
      opacity: 0.6;
      top: 10.41%;
    }
    #fourth-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 26.686%;
    }
    #fifth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.6;
      top: 46.627%;
    }
    #sixth-strip {
      height: 3px;
      width: 11.111%;
      opacity: 0.3;
      top: 56.451%;
    }
    #seventh-strip {
      height: 1px;
      width: 11.111%;
      opacity: 0.3;
      top: 59.82%;
    }
  }
}



.slider-wrapper-right{
  .numbers-enter-active,
  .numbers-leave-active,
  .second7-enter-active,
  .second7-leave-active{
    transition: all .8s linear;
  }

  .numbers-enter-from,
  .numbers-leave-to{
    opacity: 0;
  }
  .first7{
    line-height: 1.56rem;
    transition: all linear .8s;
  }
  .first7.inactive{
    font-size: 0.625rem;
    line-height: 0.625rem;
    left: 1.8rem;
  }
  .second7-enter-from,
  .second7-leave-to{
    font-size: 0.625rem;
    line-height: 0.625rem;
    left: 3.6rem;
  }
  .third7{
    transition: all linear .8s;
    opacity: 1;
  }
  .third7.inactive{
    opacity: 0;
  }
}


.slider-wrapper-left,
.slider-wrapper-right {
  .absolute {
    background: #97a3cb;
  }
}
.slider-wrapper-top {
  .menu{
    .menu-grad {
      div {
        border-radius: 50%;
        transform: scale(0);
        transition: all 0.15s linear;
      }
      .blue-b {
        position: absolute;
        width: 180.46px;
        height: 180.46px;
        left: -104px;
        top: 18px;

        background: linear-gradient(
            321.88deg,
            rgba(7, 25, 61, 0) 12.53%,
            #f22959 43.45%,
            #0085ff 60.5%
        );
        filter: blur(60px);
      }
      .blue-s {
        position: absolute;
        width: 112.05px;
        height: 112.05px;
        left: 44px;
        top: 22px;

        background: linear-gradient(
            209.3deg,
            rgba(0, 133, 255, 0) -2.55%,
            #0085ff 64.59%
        );
        filter: blur(60px);
        transform: rotate(165deg) scale(0);
      }
      .purple {
        position: absolute;
        width: 180.46px;
        height: 180.46px;
        left: -34px;
        top: 86px;

        background: linear-gradient(
            209.3deg,
            rgba(242, 137, 41, 0) -2.55%,
            #f22959 64.59%
        );
        opacity: 0.7;
        filter: blur(60px);
        transform: rotate(165deg) scale(0);
      }
      .purple-s {
        position: absolute;
        width: 180.46px;
        height: 180.46px;
        left: -70px;
        top: 47px;

        background: linear-gradient(
            321.88deg,
            rgba(7, 25, 61, 0) 12.53%,
            #f22959 43.45%,
            #0085ff 60.5%
        );
        filter: blur(60px);
      }
    }
    .menu-content{
      p{
        letter-spacing: 0.1rem;
      }
      *{
        transition: all 0.15s linear;
      }
    }
  }
  .menu.unactive {
    .menu-content:hover {
      p {
        letter-spacing: 0.3rem;
      }
      #second-menu-strip {
        width: 100%;
      }
    }
    .menu-content:hover + .menu-grad {
      div {
        transform: scale(1);
      }
      .blue-s {
        transform: rotate(165deg) scale(1);
      }
      .purple {
        transform: rotate(165deg) scale(1);
      }
    }
  }

  .connect {
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
      left: 3rem;
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
        z-index: 1;
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
        z-index: 2;
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
        z-index: 1;
      }
    }
    .connect-content:hover {
      p {
        margin-right: 3rem;
      }
      .plus {
        transform: rotate(180deg);
        background: white;
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
}
.slider-wrapper-bottom{
  svg{
    path{
      transition: all linear .3s;
      stroke: rgba(151, 163, 203, 0.6);
    }
  }
  p{
    transition: all linear .3s;
    color: rgba(151, 163, 203, 0.6);
  }
}
.slider-wrapper-bottom:hover{
  svg{
    path{
      transition: all linear .3s;
      stroke: white;
    }
  }
  p{
    transition: all linear .3s;
    color: white;
  }
}
.menu-label-enter-active,
.menu-label-leave-active{
  transition: all linear 0.075s;
}
.menu-label-enter-from,
.menu-label-leave-to{
  opacity: 0;
}
</style>
