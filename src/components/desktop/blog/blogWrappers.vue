<template>
  <div class="wrapper-left top-50 left-17.5 bottom-22 fixed">
    <div class="home relative flex items-center cursor-pointer" @click="post ? $emit('blog') :$emit('nav')">
      <svg class="mr-5 transform rotate-90" width="12" height="13" viewBox="0 0 13 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 6L7 12L13 6" stroke="#323749" stroke-linejoin="round"/>
        <path d="M6.99998 0V12" stroke="#323749" stroke-linejoin="round"/>
      </svg>
      <p class="uppercase font-medium text-xxs" style="letter-spacing: 0.1rem; color:rgba(110, 117, 141, 1) ">{{post ? text.blog :text.home }}</p>
    </div>
    <div class="h-px w-5 absolute" style="top: 25.3731%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-5 absolute" style="top: 64.9253%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-2.5 absolute" style="top: 95.3731%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-7.5 absolute" style="top: calc(100% - 1px); background:rgba(151, 163, 203, 0.3);"></div>
  </div>
  <div class="wrapper-right top-50 right-17.5 bottom-19.5 fixed">
    <div class="h-px w-7.5 absolute" style="top: 0; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-1.5 absolute" style="top: 17.0822%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-7.5 absolute" style="top: 99%; background:rgba(151, 163, 203, 0.6);"></div>
  </div>

  <a v-if="!post" href="#blog" class="wrapper-bottom absolute bottom-18 transform transition cursor-pointer z-50" style="left: 44.8%" @click="$emit('nextSlide')">
    <svg width="14" class="transform transition duration-800 rotate-180" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
      <path d="M6.99998 0V12" stroke-linejoin="round"/>
    </svg>
    <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">{{ text.back }}</p>
  </a>
</template>

<script>
export default {
  name: "agencyWrappers",
  emits: ["goHome", "blog", "nextSlide"],
  props:{
    slide:{
      type: String,
    },
    post:{
      type: Boolean,
      default: false,
    }
  },
  computed:{
    text(){
      return require("@/assets/text/fixWrappers/ru.json")
    }
  }
};
</script>

<style scoped lang="scss">
.wrapper-bottom{
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
.wrapper-bottom:hover{
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
a{
  scroll-behavior: smooth !important;
}
</style>
