<template>
  <WrapGrads :agency="agency" />
  <div class="slider-wrapper-top fixed flex left-18 right-18 top-11 z-10">
    <div class="menu cursor-pointer w-12.5">
      <div class="menu-content">
        <p class="uppercase transition-all font-medium text-xs mb-3">menu</p>
        <div class="h-5 relative w-full">
          <div
            class="absolute top-0 h-2px w-full bg-white transition-all"
          ></div>
          <div
            id="second-menu-strip"
            class="absolute bottom-0 h-2px w-1/2 bg-white transition-all"
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
    <div class="max-frai ml-52.5">
      <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
      <p
        class="uppercase inter font-bold mt-4"
        style="color: #ff2e53; letter-spacing: 1rem; line-height: 1"
      >
        AGENCY
      </p>
    </div>
    <div class="ml-27 h-full mt-auto">
      <div class="h-8px w-px" style="background: #ff2e53"></div>
    </div>
    <div class="ml-65 agency">
      <p class="font-medium text-base" @mouseover="agency = true" @mouseleave="agency = false">
        Агентство простых решений сложного <br />
        цифрового мира
      </p>
    </div>
    <div class="connect ml-auto">
      <div class="connect-content flex items-center">
        <p class="uppercase font-semibold text-xsm mr-4">СВЯЗАТЬСЯ С НАМИ</p>
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
  <div class="slider-wrapper-left fixed bottom-18 left-18 top-50">
    <div class="relative w-22.5 h-full first-state states">
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
  <div class="slider-wrapper-right fixed bottom-18 right-18 top-50">
    <div class="relative w-22.5 h-full">
      <div
        class="absolute right-0 transition-all h-px w-1/3 opacity-30"
        style="top: 0"
      ></div>
      <div
        class="absolute right-0 transition-all h-3px w-1/6 opacity-60"
        style="top: 41.34897%"
      ></div>
      <div
        class="absolute right-0 transition-all h-3px w-1/15 opacity-30"
        style="top: 43.69501466%"
      ></div>
      <div
        class="absolute flex bottom-0 right-0"
        style="background: transparent"
      >
        <div class="numbers flex mr-2">
          <p class="text-3xl" style="line-height: 0.78">1</p>
        </div>
        <div class="flex flex-col">
          <div>
            <p class="number text-xxs">7</p>
          </div>
          <div
            class="h-px w-15px mt-1"
            style="background: rgba(151, 163, 203, 0.6)"
          ></div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import WrapGrads from "@/components/WrapGrads";

export default {
  name: "wrappers",
  components: { WrapGrads },
  data() {
    return {
      menuHover: null,
      agency: false
    };
  },
};
</script>

<style lang="scss" scoped>
.slider-wrapper-left {
  .states {
    div {
      transition: all 0.2s linear;
      position: absolute;
      left: 0;
      background: #97a3cb;
    }
  }
  .first-state {
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
}
.slider-wrapper-left,
.slider-wrapper-right {
  .absolute {
    background: #97a3cb;
  }
}
.slider-wrapper-top {
  .menu {
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
</style>
