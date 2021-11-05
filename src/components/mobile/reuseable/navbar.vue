<template>
  <div class="navbar fixed flex left-0 right-0 top-0 pt-5 px-4.5">
    <div class="grads relative">
      <div class="purple"></div>
      <div class="blue"></div>
    </div>
    <div class="menu flex flex-col mr-20 relative z-10">
      <p class="menu fz-10 text-indigo-50 uppercase" style="letter-spacing: 0.3rem">{{ text.menu }}</p>
      <div class="w-10 h-0.5 mt-3 mb-3.5 bg-white"></div>
      <div class="w-5 h-0.5 bg-white"></div>
    </div>
    <div class="max-agency flex flex-col relative z-10">
      <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
      <p
        class="uppercase inter font-bold mt-4 fz-10"
        style="color: #ff2e53; letter-spacing: 0.53rem; line-height: 1"
      >
        {{ text.AGENCY }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  props:['lang'],
  computed:{
    text(){
      return require('@/assets/text/fixWrappers/' + this.lang + '.json')
    }
  }
};
</script>

<style scoped lang="scss">
.grads{
  div{
    border-radius: 50%;
  }
  .purple {
    position: absolute;
    width: 28.75rem;
    height: 28.75rem;
    left: -5.5rem;
    top: -25.15rem;
    z-index: 2;
    background: linear-gradient(321.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(242, 41, 89, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(1.85rem);
    transform: rotate(-22.14deg);
  }
  .blue {
    position: absolute;
    width: 28.75rem;
    height: 28.75rem;
    left: 5.5rem;
    top: -21.15rem;
    background: linear-gradient(344.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(0, 133, 255, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(1.85rem);
    transform: rotate(-22.14deg);
  }
}
</style>