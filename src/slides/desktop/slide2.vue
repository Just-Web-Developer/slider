<template>
  <div id="slide-2" class="slide ml-83 pt-50 h-screen">
    <div class="relative flex" style="height: max-content">
      <div class="about w-48.3p">
        <p
          class="uppercase text-xxs font-medium mb-22"
          style="color: rgba(110, 117, 141, 1); letter-spacing: 2px"
        >
          {{ text.miniTitle }}
        </p>
        <p
          class="text-xl font-medium main text-justify"
          style="line-height: 2.25rem"
        >
          {{text.mainText}}
        </p>
        <div class="w-50p flex justify-end mt-38 ml-3p">
          <img
            class="w-auto"
            src="@/assets/images/slide_2/about/team.svg"
            alt=""
          />
          <img
            class="w-auto mx-7"
            src="@/assets/images/slide_2/about/thunder.svg"
            alt=""
          />
        </div>
      </div>
      <div
        class="ml-44 h-full border-l pl-10 w-24p flex flex-col"
        style="border-color: rgba(151, 163, 203, 0.3); height: auto"
      >
        <p
          class="uppercase text-xxs ml-2"
          style="letter-spacing: 2px; color: rgba(255, 46, 83, 1)"
        >
          {{text.ready}}
        </p>
        <div class="stack-slider relative overflow-y-hidden h-70p mt-12.5">
          <div
            class="relative h-full"
            style="transition: all linear 0.5s"
            :style="'top:-' + 33.3 * stackState + '%'"
          >
            <template
              v-for="(stackSlide, index) in text.stackSlider"
              :key="index.id"
            >
              <transition mode="out-in" name="fade">
                <div
                  v-if="
                    index === stackState ||
                    index === stackState + 1 ||
                    index === stackState + 2
                  "
                  class="flex stack-slide absolute h-1/3 py-4 items-center"
                  :style="'top:' + index * 33.3 + '%'"
                >
                  <img
                    :src="
                      require('@/assets/images/slide_2/stack/' +
                        stackSlide.image +
                        '.svg')
                    "
                    class="h-19 w-19 p-3.75 rounded-full"
                    style="background: rgba(110, 117, 141, 0.2)"
                    alt=""
                  />
                  <p
                    class="text-base font-medium ml-5"
                    style="line-height: 1.5rem"
                  >
                    {{ stackSlide.text }}
                  </p>
                </div>
              </transition>
            </template>
          </div>
        </div>
        <div class="mt-12 flex">
          <img
            class="stack-arrow cursor-pointer transform rotate-90 p-2.5 rounded-full w-10 h-10"
            @click="stackPrev()"
            src="@/assets/images/slide_2/stack/arrow.svg"
            alt=""
          />
          <img
            class="stack-arrow cursor-pointer transform -rotate-90 p-2.5 rounded-full ml-4 w-10 h-10"
            @click="stackNext()"
            src="@/assets/images/slide_2/stack/arrow.svg"
            alt=""
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide2",
  data() {
    return {
      stackState: 0,
      stackDirection: "stack-up"
    };
  },
  computed:{
    text(){
      return require("@/assets/text/main/slide2/ru.json")
    }
  },
  methods: {
    stackNext() {
      if (this.stackState < this.text.stackSlider.length - 3) {
        this.stackState++;
      }
    },
    stackPrev() {
      if (this.stackState > 0) {
        this.stackState--;
      }
    },
  },
};
</script>

<style lang="scss" scoped>
.about > .main {
  text-indent: 17rem;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 0.3s ease-in;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.stack-arrow {
  transition: all linear 0.3s;
  &:hover {
    background: white;
  }
}
</style>
