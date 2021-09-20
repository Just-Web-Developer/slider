<template>
  <div id="slide-3" class="slide ml-83 pt-49 h-screen relative flex">
    <div
      class="clients-left w-68 pr-2 flex flex-col pr-16"
      style="height: fit-content"
    >
      <p
        class="uppercase text-xxs font-medium"
        style="letter-spacing: 2px; color: rgba(110, 117, 141, 1)"
      >
        OUR CLIENTS
      </p>
      <p class="mt-12 text-base" style="line-height: 1.5rem">
        Нам доверяют решение цифровых задач компании-лидеры в своих сферах
      </p>
      <h2
        class="mt-58.5 flex"
        style=" font-size: 4rem; color: #FF2E53 line-height: 4rem"
      >
        129
      </h2>
      <p
        class="mt-2.5 font-medium uppercase text-xxs"
        style="line-height: 200%; color: rgba(192, 197, 216, 1)"
      >
        РЕАЛИЗОВАННЫХ <br />
        проектов
      </p>
    </div>
    <div class="clients-right mt-1 flex flex-col">
      <div class="client-slider relative" style="height: fit-content">
        <transition name="client-1">
          <div
            v-if="clientSlide === 1"
            class="client-1 absolute grid grid-cols-4 grid-rows-2 gap-0 w-250"
          >
            <div
              class="client flex justify-center items-center h-62.5 w-62.5"
              v-for="client in clientSlider[0]"
              :key="client.id"
              :class="client.opacity"
            >
              <img
                :src="
                  require('@/assets/images/slide_3/' + client.image + '.svg')
                "
                alt=""
              />
            </div>
          </div>
        </transition>
        <transition name="client-2">
          <div v-if="clientSlide === 2" class="client-2 absolute flex w-250">
            <div class="grid grid-cols-2 grid-rows-2 gap-0 w-1/2">
              <div
                class="client flex justify-center items-center h-62.5 w-62.5"
                v-for="client in clientSlider[1]"
                :key="client.id"
                :class="client.opacity"
              >
                <img
                  :src="
                    require('@/assets/images/slide_3/' + client.image + '.svg')
                  "
                  alt=""
                />
              </div>
            </div>
            <div class="w-1/2 flex flex-col ">
              <p
                class="ml-37.5 mt-50p font-medium text-base w-45p"
                style="line-height: 1.5rem; color: #c0c5d8"
              >
                Мы готовы быстро и легко решить все твои сложные цифровые
                проблемы
              </p>
              <div class="mt-auto ml-37.5 become-client  " @click="$emit('contact')" >
                <div class="connect-content flex cursor-pointer justify-start items-center" >
                  <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
                    <div
                      class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                    ></div>
                    <div
                      class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                    ></div>
                  </div>
                  <p class="uppercase font-semibold text-xxsm">стать клиентом</p>
                </div>

                <div class="connect-grad relative" style="z-index: -1">
                  <div id="grad-1"></div>
                  <div id="grad-2"></div>
                  <div id="grad-3"></div>
                </div>
              </div>
            </div>
          </div>
        </transition>
      </div>
      <div class="paginations flex ml-64.5 mt-137">
        <div
          class="pagination"
          :class="
            clientSlide === 1
              ? 'active w-10 h-1 rounded-lg'
              : 'w-1.5 h-1.5 bg-white rounded-full'
          "
        ></div>
        <div
          class="pagination ml-5"
          :class="
            clientSlide === 2
              ? 'active w-10 h-1 rounded-lg'
              : 'w-1.5 h-1.5 bg-white rounded-full'
          "
        ></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide3",
  props: ["clientSlide"],
  emits:['contact'],
  data() {
    return {
      clientSlider: [
        [
          {
            image: "atlas",
            opacity: "second",
          },
          {
            image: "playboy",
            opacity: "first",
          },
          {
            image: "digital",
            opacity: "second",
          },
          {
            image: "sluhay",
            opacity: "first",
          },
          {
            image: "twn",
            opacity: "first",
          },
          {
            image: "mgu",
            opacity: "second",
          },
          {
            image: "m1",
            opacity: "first",
          },
          {
            image: "parimatch",
            opacity: "second",
          },
        ],
        [
          {
            image: "unn",
            opacity: "second",
          },
          {
            image: "tk",
            opacity: "first",
          },
          {
            image: "sw",
            opacity: "first",
          },
          {
            image: "jn",
            opacity: "second",
          },
        ],
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.client {
  transition: all linear 0.4s;
  &.first {
    background: rgba(110, 117, 141, 0.1);
  }
  &.second {
    background: rgba(110, 117, 141, 0.2);
  }
  transition: all linear 0.4s;
  img {
    transition: all linear 0.4s;
  }
}
.client:hover{
  background: #FF2E53;
}
</style>
