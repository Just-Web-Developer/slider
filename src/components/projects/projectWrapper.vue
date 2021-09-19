<template>
  <div class="wrapper-left top-50 left-17.5 bottom-22 fixed">
    <div class="home relative flex items-center cursor-pointer" @click="$emit('projects')">
      <svg class="mr-5 transform rotate-90" width="12" height="13" viewBox="0 0 13 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 6L7 12L13 6" stroke="#323749" stroke-linejoin="round"/>
        <path d="M6.99998 0V12" stroke="#323749" stroke-linejoin="round"/>
      </svg>
      <p class="uppercase font-medium text-xxs" style="letter-spacing: 0.1rem; color:rgba(110, 117, 141, 1) ">PROJECTS</p>
    </div>
    <div class="h-px w-5 absolute" style="top: 25.00%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-5 absolute" style="top: 62.5%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-2.5 absolute" style="top: 92.65%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-7.5 absolute" style="top: calc(100% - 1px); background:rgba(151, 163, 203, 0.3);"></div>
  </div>
  <div class="wrapper-right top-50 right-17.5 bottom-19.5 fixed">
    <div class="h-px w-7.5 absolute" style="top: 0; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-1.5 absolute" style="top: 17.0822%; background:rgba(151, 163, 203, 0.3);"></div>
    <div class="h-px w-7.5 absolute" style="top: 99%; background:rgba(151, 163, 203, 0.6);"></div>
  </div>
</template>

<script>
export default {
  name: "projectWrapper",
  emits:['projects']
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
</style>
