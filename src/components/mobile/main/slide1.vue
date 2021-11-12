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

    <section class="services fz-16 font-medium flex flex-col mb-33.75">
      <div class="service-m flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[0] = !adds[0]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/loader.svg"  alt="">
          <p class="fz-18 uppercase" style="line-height: 1.666rem">Создаём</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[0], 'h-0 p-0': !adds[0] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Приложения</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Креативы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service-m flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[1] = !adds[1]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/globe.svg"  alt="">
          <p class="fz-18 uppercase" style="line-height: 1.666rem">ВЕДЁМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[1], 'h-0 p-0': !adds[1] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Бренды</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Страницы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service-m flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[2] = !adds[2]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/radio.svg"  alt="">
          <p class="fz-18 uppercase" style="line-height: 1.666rem">ПРОДВИГАЕМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[2], 'h-0 p-0': !adds[2] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Бренды</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Сайты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Страницы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service-m flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[3] = !adds[3]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/pen-tool.svg"  alt="">
          <p class="fz-18 uppercase" style="line-height: 1.666rem">ПИШЕМ</p>
        </div>
        <div class="dop overflow-hidden  grid grid-rows-3 grid-cols-1 gap-1.25" :class="{'h-31.25 pt-2.5 pb-7.5': adds[3], 'h-0 p-0': !adds[3] }">
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Стратегии</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Сервисы</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
          <div class="flex items-center ml-auto justify-end">
            <p class="mr-5" style="line-height: 1.5625;">Тексты</p>
            <div class="w-5 h-5 relative">
              <div class="w-px h-4 absolute top-0.5 left-1/2 transform -translate-x-1/2" style="background:rgba(110, 117, 141, 1);"></div>
              <div class="h-px w-4 absolute left-0.5 top-1/2 transform -translate-y-1/2" style="background:rgba(110, 117, 141, 1);"></div>
            </div>
          </div>
        </div>
      </div>

      <div class="service-m flex flex-col px-7.5 mx-4.5 mb-2.5" @click="adds[4] = !adds[4]">
        <div class="flex items-center justify-between py-3.75 ">
          <img class="w-12.5 h-12.5" src="@/assets/images/slide_1/service_icons/smile.svg"  alt="">
          <p class="fz-18 uppercase" style="line-height: 1.666rem">ПОМОГАЕМ</p>
        </div>
        <div class="dop overflow-hidden flex" :class="{'h-31.25 pt-2.5 pb-7.5': adds[4], 'h-0 p-0': !adds[4] }">
          <div class="flex items-center ml-auto w-55p text-right mt-auto justify-end items-end">
            <p  style="line-height: 1.5625;">Решать задачи любой сложности</p>
          </div>
        </div>
      </div>
    </section>
    <!--    First section END-->
    <!--    Second section START-->

    <section class="slide-2 flex flex-col overflow-hidden ">
      <div class="header flex justify-between items-center mx-4.5 mb-7.5">
        <p class="fz-10 font-medium color-gray uppercase" style="line-height: 1;letter-spacing: 0.3em">ABOUT</p>
        <div class="flex icons">
          <svg class="mr-6" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path stroke-opacity="0.3" d="M28.3333 35V31.6667C28.3333 29.8986 27.631 28.2029 26.3807 26.9526C25.1305 25.7024 23.4348 25 21.6667 25H8.33334C6.56523 25 4.86954 25.7024 3.61929 26.9526C2.36905 28.2029 1.66667 29.8986 1.66667 31.6667V35" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path stroke-opacity="0.3" d="M15 18.3333C18.6819 18.3333 21.6667 15.3486 21.6667 11.6667C21.6667 7.98477 18.6819 5 15 5C11.3181 5 8.33334 7.98477 8.33334 11.6667C8.33334 15.3486 11.3181 18.3333 15 18.3333Z" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path stroke-opacity="0.3" d="M38.3333 35V31.6667C38.3322 30.1896 37.8406 28.7546 36.9356 27.5872C36.0306 26.4198 34.7636 25.586 33.3333 25.2167" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            <path stroke-opacity="0.3" d="M26.6667 5.21667C28.1007 5.58384 29.3717 6.41784 30.2794 7.58719C31.1871 8.75654 31.6797 10.1947 31.6797 11.675C31.6797 13.1553 31.1871 14.5935 30.2794 15.7628C29.3717 16.9322 28.1007 17.7662 26.6667 18.1333" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
          <svg width="32" height="36" viewBox="0 0 32 36" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path stroke-opacity="0.3" d="M17.6667 1.33333L1 21.3333H16L14.3333 34.6667L31 14.6667H16L17.6667 1.33333Z" stroke="#97A3CB" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </div>
      </div>
      <p class="fz-16 font-medium mb-25 mx-4.5" style="line-height: 1.875;">
        Агентство комплексных решений цифровых задач известного киевского программиста Макса Фрая. Команда разработчиков, дизайнеров, креативщиков и просто ответственных ребят, которые вместе решают все ваши проблемы быстро и круто. Готовы изменить ваш мир к лучшему.
      </p>
      <span class="fz-10 ml-4.5 font-medium color-accent mb-7.5 uppercase" style="line-height: 1;letter-spacing: 0.3rem">READY FOR USE PRODUCTS</span>
      <slider></slider>
    </section>

    <!--    Second section END-->

  </div>

</template>

<script>
import firstAnimation from "../../desktop/slide1/firstAnimation";
import slider from "../reuseable/slider";

export default {
  name: "slide1",
  components:{firstAnimation, slider},
  data(){
    return{
      adds:[false,false,false,false,false]
    }
  }
};
</script>

<style scoped lang="scss">
  .service-m{
    background: rgba(110, 117, 141, 0.1);
  }
  .dop{
    transition: all 0.35s ease-out;
  }
  .slide-2{
    .header{
      .icons{
        svg{
          width: 2.5rem;
        }
      }
    }
  }
</style>