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

    <div class="services grid grid-cols-1 grid-rows-5 gap-2.5">
      <div class="service flex items-center justify-between px-7.5 py-3.75 mx-4.5">
        <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/loader.svg"  alt="">
        <p class="fz-18 font-medium uppercase">Создаём</p>
      </div>

      <div class="service flex items-center justify-between px-7.5 py-3.75 mx-4.5">
        <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/globe.svg"  alt="">
        <p class="fz-18 font-medium uppercase">ВЕДЁМ</p>
      </div>

      <div class="service flex items-center justify-between px-7.5 py-3.75 mx-4.5">
        <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/radio.svg"  alt="">
        <p class="fz-18 font-medium uppercase">ПРОДВИГАЕМ</p>
      </div>

      <div class="service flex items-center justify-between px-7.5 py-3.75 mx-4.5">
        <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/pen-tool.svg"  alt="">
        <p class="fz-18 font-medium uppercase">ПИШЕМ</p>
      </div>

      <div class="service flex items-center justify-between px-7.5 py-3.75 mx-4.5">
        <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/smile.svg"  alt="">
        <p class="fz-18 font-medium uppercase">ПОМОГАЕМ</p>
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
  components:{firstAnimation}
};
</script>

<style>
  .service{
    background: rgba(110, 117, 141, 0.1);
  }
</style>