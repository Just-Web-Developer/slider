<template>
  <div id="slide-7" class="slide mx-83 pt-67 pb-40 h-screen relative flex flex-col h-125">
    <div class="flex justify-between">
      <p class="text-3.55xl w-87.5">{{ text.letsTalk }}</p>
      <img src="@/assets/images/slide_7/targe.svg" class="w-12.5 h-12.5" alt="">
    </div>
    <div class="flex flex-col">
      <p class="w-87.5 text-lg mb-25 ml-44p" style="color: rgba(192, 197, 216, 1); line-height: 1.875rem;">{{ text.weReady }}</p>
      <div class="mt-auto become-client ml-44p ">
        <div class="connect-content flex justify-start items-center cursor-pointer w-max" @click="$emit('contact')">
          <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
            <div
              class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
            ></div>
            <div
              class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
            ></div>
          </div>
          <p class="uppercase font-semibold text-xxsm">{{ text.become }}</p>
        </div>

        <div class="connect-grad relative" style="z-index: -1">
          <div id="grad-1"></div>
          <div id="grad-2"></div>
          <div id="grad-3"></div>
        </div>
      </div>
    </div>
    <div class="flex justify-between mt-auto">
      <p class="text-xxs font-medium" style="letter-spacing: 2px; color: rgba(110, 117, 141, 1)">
        {{ text.maxFrai }}
      </p>
      <div class="h-px w-87.5" style="background:rgba(151, 163, 203, 0.3);"></div>
      <div class="w-5 h-px" style="background:rgba(151, 163, 203, 0.6);"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide7",
  emits:['contact'],
  computed:{
    text(){
      return require("src/assets/text/main/slide7/ru.json")
    }
  }
};
</script>

<style lang="scss" scoped>

</style>
