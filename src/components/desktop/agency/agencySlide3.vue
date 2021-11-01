<template>
  <div class="pt-50 px-82.5 flex slide">
    <h4 class="fz-301 mt-74 w-86.25 flex-shrink-0" style="color:#FF2E53 ">{{ text.mainRule }}</h4>
    <div class="right-side ml-43.75">
      <picture class="mr-22.5">
        <svg width="32" height="36" viewBox="0 0 32 36" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path stroke-opacity="0.3" d="M17.6667 1.33333L1 21.3333H16L14.3333 34.6667L31 14.6667H16L17.6667 1.33333Z" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </picture>
      <p class="mt-13.25 fz-18" style="color:#C0C5D8">{{ text.text[0] }} </p>
      <p class="mt-25 fz-201 font-medium">{{ text.text[1] }} </p>
    </div>
  </div>
</template>

<script>
export default {
  name: "agencySlide3",
  props:['lang'],
  computed:{
    text(){
      return require("@/assets/text/agency/slide3/ru.json")
    }
  }
};
</script>

<style scoped>

</style>