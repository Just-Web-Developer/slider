<template>
  <div class="pt-50 pl-115 flex flex-col slide">
    <h4 class="fz-301 ml-97.5 mb-12.5 flex-shrink-0" style="color:#6E758D ">{{ text.what }}</h4>
    <div class="services grid w-max gris-cols-3 grid-rows-2 gap-10">
      <div class="row-start-1 w-87.5 h-56.25 col-start-1 pl-8.5 pt-8.5 pb-7.5 pr-7.5 col-span-1 row-span-1 flex flex-col justify-between" style="background: rgba(110, 117, 141, .1)">
        <div class="flex justify-between items-center">
          <img src="@/assets/images/slide_1/service_icons/loader.svg" class="h-10" alt="">
          <p class="uppercase font-medium fz-201">{{ text.services[0].title }}</p>
        </div>
        <div class="flex flex-col items-end ml-auto">
          <p class="text-left">
            {{ text.services[0].points[0] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[0].points[1] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[0].points[2] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
        </div>
      </div>
      <div class="row-start-1 w-87.5 h-56.25 col-start-2 pl-8.5 pt-8.5 pb-7.5 pr-7.5 col-span-1 row-span-1 flex flex-col justify-between" style="background: rgba(110, 117, 141, .1)">
        <div class="flex justify-between items-center">
          <img src="@/assets/images/slide_1/service_icons/globe.svg" class="h-10" alt="">
          <p class="uppercase font-medium fz-201">{{ text.services[1].title }}</p>
        </div>
        <div class="flex flex-col items-end ml-auto">
          <p class="text-left">
            {{ text.services[1].points[0] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[1].points[1] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[1].points[2] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
        </div>
      </div>
      <div class="row-start-1 w-87.5 h-56.25 col-start-3 pl-8.5 pt-8.5 pb-7.5 pr-7.5 col-span-1 row-span-1 flex flex-col justify-between" style="background: rgba(110, 117, 141, .1)">
        <div class="flex justify-between items-center">
          <img src="@/assets/images/slide_1/service_icons/radio.svg" class="h-10" alt="">
          <p class="uppercase font-medium fz-201">{{ text.services[2].title }}</p>
        </div>
        <div class="flex flex-col items-end ml-auto">
          <p class="text-left">
            {{ text.services[2].points[0] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[2].points[1] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[2].points[2] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
        </div>
      </div>
      <div class="row-start-2 w-87.5 h-56.25 col-start-2 pl-8.5 pt-8.5 pb-7.5 pr-7.5 col-span-1 row-span-1 flex flex-col justify-between" style="background: rgba(110, 117, 141, .1)">
        <div class="flex justify-between items-center">
          <img src="@/assets/images/slide_1/service_icons/pen-tool.svg" class="h-10" alt="">
          <p class="uppercase font-medium fz-201">{{ text.services[3].title }}</p>
        </div>
        <div class="flex flex-col items-end ml-auto">
          <p class="text-left">
            {{ text.services[3].points[0] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[3].points[1] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
          <p class="text-left">
            {{ text.services[3].points[2] }}
            <img src="@/assets/images/slide_1/service_icons/cross.svg" class="inline ml-4" alt="" />
          </p>
        </div>
      </div>
      <div class="row-start-2 w-87.5 h-56.25 col-start-3 pl-8.5 pt-8.5 pb-7.5 pr-7.5 col-span-1 row-span-1 flex flex-col justify-between" style="background: rgba(110, 117, 141, .1)">
        <div class="flex justify-between items-center">
          <img src="@/assets/images/slide_1/service_icons/smile.svg" class="h-10" alt="">
          <p class="uppercase font-medium fz-201">{{ text.services[4].title }}</p>
        </div>
        <div class="flex flex-col items-end ml-auto">
          <p style="line-height: 1.9375rem">{{ text.services[4].points[0] }}</p>
          <p style="line-height: 1.9375rem">{{ text.services[4].points[1] }}</p>
        </div>
      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "agencySlide4",
  props:['lang'],
  computed:{
    text(){
      return require("@/assets/text/agency/slide4/ru.json")
    }
  }
};
</script>

<style scoped>

</style>