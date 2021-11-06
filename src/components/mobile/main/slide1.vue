<template>
  <div style="color: white">


<!--    First section START-->
    <firstAnimation class="relative h-125 w-screen overflow-hidden" :mobile="true"/>


    <h2 class="px-4.5 w-screen fz-22 -mt-11 mb-12.5" style="line-height: 1.875rem;">Агентство простых решений сложного цифрового мира</h2>
    <div class="flex px-4.5 w-screen mb-25">
      <div class="news pt-2 flex flex-col flex-shrink-0 mr-10" style="color:rgba(255, 46, 83, 1);">
        <p class="mb-6 fz-10">HOT NEWS</p>
        <svg
          width="20"
          height="20"
          viewBox="0 0 20 20"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke="#ff2e53"
            d="M12 17L19 10L12 3"
            stroke-width="2"
            stroke-linejoin="round"
          />
          <path d="M5 10L19 10" stroke="#ff2e53" stroke-width="2" stroke-linejoin="round" />
        </svg>
      </div>
      <p class="fz-15 font-medium" style="line-height: 1.6; color: rgba(192, 197, 216, 1)">
        Max Frai Agency & Atlas Weekend: технические решения для масшатбных проектов в условиях пандемии
      </p>
    </div>

    <div class="services flex flex-col">
      <div class="service flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[0] = !adds[0]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/loader.svg"  alt="">
          <p class="fz-18 font-medium uppercase">Создаём</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[0], 'h-0 p-0': !adds[0] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[0] = !adds[0]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/globe.svg"  alt="">
          <p class="fz-18 font-medium uppercase">ВЕДЁМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[0], 'h-0 p-0': !adds[0] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[1] = !adds[1]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/radio.svg"  alt="">
          <p class="fz-18 font-medium uppercase">ПРОДВИГАЕМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[1], 'h-0 p-0': !adds[1] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[0] = !adds[0]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/pen-tool.svg"  alt="">
          <p class="fz-18 font-medium uppercase">ПИШЕМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[0], 'h-0 p-0': !adds[0] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[0] = !adds[0]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/smile.svg"  alt="">
          <p class="fz-18 font-medium uppercase">ПОМОГАЕМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[0], 'h-0 p-0': !adds[0] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <!--    First section END-->
    <!--    Second section START-->

    <!--    Second section END-->

  </div>

</template>

<script>
import firstAnimation from "../../desktop/slide1/firstAnimation";

export default {
  name: "slide1",
  components:{firstAnimation},
  data(){
    return{
      adds:[false,false,false,false,false]
    }
  }
};
</script>

<style scoped>
  .service{
    background: rgba(110, 117, 141, 0.1);
  }
  .dop{
    transition: all 0.35s ease-out;
  }
</style>