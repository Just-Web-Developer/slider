<template>
  <div class="body overflow-hidden" :class="'slide-'+slide">
    <FixWrapper @nextSlide="nextSlide()" @prevSlide="prevSlide()" :state="slide" class="z-50" />
    <div id="slide-1" @scroll.stop="" class="slide ml-83 pt-23.5 h-screen relative">
      <servicesScreen />
      <firstAnimation/>
      <div class="news flex mt-18.75 ml-66 cursor-pointer w-max">
        <div>
          <p class="font-medium uppercase text-xxs" style="letter-spacing: 0.3em;color: #FF2E53;">HOT NEWS</p>
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 17L19 10L12 3" stroke-width="2" stroke-linejoin="round"/>
            <path d="M5 10L19 10" stroke-width="2" stroke-linejoin="round"/>
          </svg>
        </div>
        <div class="ml-47 right">
          <p class="font-medium text-xsm relative -top-2">
            Max Frai Agency & Atlas <br> Weekend: технические решения <br> для масшатбных проектов в <br> условиях пандемии
          </p>
        </div>
      </div>
    </div>
    <div class="gradient">
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: -518px;top: 107px;background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 133, 255, 0) 100%);"></div>
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: -322px;top: 391px;background: radial-gradient(50% 50% at 50% 50%, rgba(242, 41, 89, 0.3) 0%, rgba(242, 41, 89, 0) 100%);"></div>
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: 101px;top: 779px;background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 128, 247, 0) 100%);"></div>
    </div>
    <div id="slide-2" class="slide ml-83 mt-23.5 pt-27.5 h-screen " >
      <div class="relative flex" style="height: max-content">
        <div class="about w-47p">
          <p class="uppercase text-xxs font-medium mb-30" style="color:rgba(110, 117, 141, 1);letter-spacing: 2px">about</p>
          <p class="text-xl font-medium main text-justify" style="line-height: 2.25rem">Агентство комплексных решений цифровых задач известного киевского программиста Макса Фрая. Команда разработчиков, дизайнеров, креативщиков и просто ответственных ребят, которые вместе решают все ваши проблемы быстро и круто. Готовы изменить ваш мир к лучшему. </p>
          <div class="w-50p flex justify-end  mt-38 ml-3p">
            <img class="w-auto" src="./assets/images/slide_2/about/team.svg" alt="">
            <img class="w-auto mx-7" src="./assets/images/slide_2/about/thunder.svg" alt="">
          </div>
        </div>
        <div class="ml-44 h-full border-l pl-10 w-24p flex flex-col" style="border-color: rgba(151, 163, 203, 0.3);height: auto">
          <p class="uppercase text-xxs ml-2" style="letter-spacing: 2px;color: rgba(255, 46, 83, 1)" >READY FOR USE PRODUCTS</p>
          <div class="stack-slider relative overflow-y-hidden h-70p mt-16.5">
            <div class="relative h-full" style="transition: all linear 0.5s" :style="'top:-'+(33.3*slide2.stackState)+'%'" >
              <template v-for="(stackSlide, index) in data.stackSlider" :key="index.id">
                <transition mode="out-in"  name="fade">
                  <div v-if="slide2.stackState === 0 && index === 0 || slide2.stackState === 1 && index === 3" class="flex stack-slide absolute h-1/3 items-center"   :style="'top:'+(index*33.3)+'%'"  >
                    <img :src="require('./assets/images/slide_2/stack/'+stackSlide.image+'.svg')" class="h-19 w-19 p-4 rounded-full" style="background:rgba(110, 117, 141, .2);" alt="">
                    <p class="text-base font-medium ml-5" style="line-height: 1.5rem">{{stackSlide.text}}</p>
                  </div>
                </transition>
                <div v-if="index !== 0 && index !== 3" class="flex stack-slide absolute h-1/3 items-center"   :style="'top:'+(index*33.3)+'%'"  >
                  <img :src="require('./assets/images/slide_2/stack/'+stackSlide.image+'.svg')" class="h-19 w-19 p-4 rounded-full" style="background:rgba(110, 117, 141, .2);" alt="">
                  <p class="text-base font-medium ml-5" style="line-height: 1.5rem">{{stackSlide.text}}</p>
                </div>
              </template>
            </div>
          </div>
          <div class="mt-auto flex">
            <img class="stack-arrow cursor-pointer transform rotate-90 p-2.5 rounded-full w-10 h-10" @click="stackPrev()" src="./assets/images/slide_2/stack/arrow.svg" alt="">
            <img class="stack-arrow cursor-pointer transform -rotate-90 p-2.5 rounded-full ml-4 w-10 h-10" @click="stackNext()" src="./assets/images/slide_2/stack/arrow.svg" alt="">
          </div>

        </div>
      </div>

    </div>
    <div class="gradient" style="z-index: -10;transition:all linear 1s ;position: absolute;width: 1122px;height: 1122px;left: 1200px;top:145.913vh;background: radial-gradient(50% 50% at 50% 50%, rgba(255, 46, 83, 0.3) 0%, rgba(255, 46, 83, 0) 100%);" ></div>
    <div id="slide-3" class="slide ml-83 mt-23.5 h-screen relative flex">
      <div class="clients-left  w-68 pr-2 flex flex-col pr-16" style="height: fit-content">
        <p class="uppercase text-xxs font-medium" style="letter-spacing: 2px; color:rgba(110, 117, 141, 1) ">OUR CLIENTS</p>
        <p class="mt-12 text-base" style="line-height: 1.5rem">Нам доверяют решение цифровых задач компании-лидеры в своих сферах</p>
        <h2 class="mt-58.5 flex" style="color: #FF2E53; font-size: 4rem; line-height: 4rem;">129</h2>
        <p class="mt-2.5 font-medium uppercase text-xxs" style="line-height: 200%; color: rgba(192, 197, 216, 1)">РЕАЛИЗОВАННЫХ <br> проектов</p>
      </div>
      <div class="clients-right flex flex-col " >
        <div class="client-slider relative" style="height: fit-content">
          <transition name="client-1">
            <div v-if="slide3.clientSlide===1" class="client-1 absolute grid grid-cols-4 grid-rows-2 gap-0 w-250">
              <div class="client flex justify-center items-center h-62.5 w-62.5 " v-for="client in data.clientSlider[0]" :key="client.id" :class="client.opacity">
                <img :src="require('../src/assets/images/slide_3/' + client.image+'.svg')" alt="">
              </div>
            </div>
          </transition>
          <transition name="client-2">
            <div v-if="slide3.clientSlide===2" class="client-2 absolute flex w-250">
              <div class="grid grid-cols-2 grid-rows-2 gap-0 w-1/2">
                <div class="client flex justify-center items-center h-62.5 w-62.5" v-for="client in data.clientSlider[1]" :key="client.id" :class="client.opacity">
                  <img :src="require('../src/assets/images/slide_3/' + client.image+'.svg')" alt="">
                </div>
              </div>
              <div class="w-1/2 flex flex-col items-center">
                <p class="mt-50p font-medium text-base w-45p" style="line-height: 1.5rem;color: #C0C5D8">Мы готовы быстро и легко решить все твои сложные цифровые проблемы</p>
                <div class="mt-auto become-client mx-auto cursor-pointer">
                  <div class="connect-content flex justify-start items-center">
                    <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
                      <div
                        class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                      ></div>
                      <div
                        class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                      ></div>
                    </div>
                    <p class="uppercase font-semibold text-xsm ">стать клиентом</p>
                  </div>

                  <div class="connect-grad relative" style="z-index: -1">
                    <div id="grad-1"></div>
                    <div id="grad-2"></div>
                    <div id="grad-3"></div>
                  </div>
                </div>
              </div>
            </div>
          </transition>
        </div>
        <div class="paginations flex ml-64.5 mt-137">
          <div class="pagination " :class="slide3.clientSlide === 1 ? 'active w-10 h-1 rounded-lg' : 'w-1.5 h-1.5 bg-white rounded-full'"></div>
          <div class="pagination ml-5" :class="slide3.clientSlide === 2 ? 'active w-10 h-1 rounded-lg' : 'w-1.5 h-1.5 bg-white rounded-full'"></div>
        </div>



      </div>
    </div>
  </div>

</template>

<script>
import FixWrapper from "@/components/FixWrapper";
import servicesScreen from "@/components/servicesScreen";
import firstAnimation from "@/components/firstAnimation";

export default {
  name: "App",
  components: {
    FixWrapper,
    servicesScreen,
    firstAnimation
  },
  data(){
    return{
      slide: 1,
      max:7,
      slide2:{
        stackState:0,
        stackDirection:"stack-up"
      },
      slide3:{
        clientSlide:1
      },
      data:{
        "stackSlider":[
          {"image":"enter", "text": "Cистема входа, учета сотрудников по заданным параметрам"},
          {"image":"layout", "text": "Готовые решения для сайтов: магазины, новостные ресурсы"},
          {"image":"send", "text": "Телеграм-боты"},
          {"image":"enter", "text": "Cистема входа, учета сотрудников по заданным параметрам"},
        ],
        "clientSlider":[
          [
            {
              image:"atlas",
              opacity:'second'
            },
            {
              image:"playboy",
              opacity:'first'
            },
            {
              image:"digital",
              opacity:'second'
            },
            {
              image:"sluhay",
              opacity:'first'
            },
            {
              image:"twn",
              opacity:'first'
            },
            {
              image:"mgu",
              opacity:'second'
            },
            {
              image:"m1",
              opacity:'first'
            },
            {
              image:"parimatch",
              opacity:'second'
            }
          ],
          [
            {
              image:"atlas",
              opacity:'second'
            },
            {
              image:"playboy",
              opacity:'first'
            },
            {
              image:"digital",
              opacity:'second'
            },
            {
              image:"sluhay",
              opacity:'first'
            }
          ]

        ]
      }
    }
  },
  methods:{
    nextSlide(){
      if(this.slide === 3 && this.slide3.clientSlide === 1){
        this.slide3.clientSlide = 2
        return
      }
      if (this.slide <= this.max){
        this.slide++
      }
      else{
        this.slide = 1
      }
    },
    prevSlide(){
      if(this.slide === 3 && this.slide3.clientSlide === 2){
        this.slide3.clientSlide = 1
        return
      }
      if (this.slide !== 1){
        this.slide--
      }
    },
    stackNext(){
      this.slide2.stackState=1
    },
    stackPrev(){
      this.slide2.stackState=0

    }
  }
};
</script>

<style lang="scss">
#app{
  height: 100vh;
}
.body{
  font-family: 'Montserrat', sans-serif;
  color: white;
  position: relative;
  transition: all linear 1s;
  top: 0;
  bottom: 0;
}
.body.slide-1{
  margin-top: 0;
  height: 100vh;
}
.body.slide-2{
  margin-top: -100vh;
  height: 200vh;
}
.body.slide-3{
  margin-top:-200vh;
}
.body.slide-4{
  margin-top:-300vh;
}
.body.slide-5{
  margin-top:-400vh;
}
.body.slide-6{
  margin-top:-500vh;
}
.body.slide-7{
  margin-top:-600vh;
}

//1 slide
.news{
  .right{
    p{
      transition: all linear .3s;
      color: #C0C5D8;
    }
  }
  svg{
    margin-left: 0;
    margin-top: 2rem;
    transition: all linear .3s;
    path{
      transition: all linear .3s;

      stroke: white;
    }
  }
}
.news:hover{
  svg{
    margin-left: 3.5rem;
    transition: all linear .3s;
    path{
      transition: all linear .3s;

      stroke: #FF2E53;
    }
  }
  .right{
    p{
      transition: all linear .3s;
      color: white;
    }
  }
}

//2 slide
.about > .main{
    text-indent: 17rem;
}

.fade-enter-active,
.fade-leave-active{
  transition: all 0.3s ease-in;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;

}

.stack-arrow{
  transition: all linear 0.3s;
  &:hover{
    background: white;
  }
}

//3 slide
.client{
  &.first{
    background: rgba(110, 117, 141,.1);
  }
  &.second{
    background: rgba(110, 117, 141,.2);
  }
  transition: all linear .4s;
  img{
    transition: all linear .4s;
  }
}

.client:hover{
  background: rgba(255, 46, 83, 1);
  img{
    transform: scale(1.3);
  }
}
.pagination{
  transition: all linear .8s;
}
.pagination.active{
  background: rgba(255, 46, 83, 1);
}

.client-1-enter-active,
.client-1-leave-active,
.client-2-enter-active,
.client-2-leave-active{
  transition: all .8s linear;
}

.client-1-enter-from,
.client-1-leave-to {
  opacity: 0;
  transform: translateX(-100%);
}
.client-2-enter-from,
.client-2-leave-to {
  opacity: 0;
  transform: translateX(100%);
}
.become-client {
  p,
  .plus,
  .plus div {
    transition: all 0.2s linear;
  }
  .plus {
    background: #ff2e53;
    div {
      background: white;
    }
  }
  .connect-grad {
    left: -11rem;
    top: -3rem;
    div {
      border-radius: 50%;
      transform: scale(0);
      transition: all 0.15s linear;
    }
    #grad-1 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 66px;
      top: -90px;

      background: linear-gradient(
          321.88deg,
          rgba(7, 25, 61, 0) 12.53%,
          #f22959 43.45%,
          #ff0000 60.5%
      );
      filter: blur(60px);
    }
    #grad-2 {
      position: absolute;
      width: 112.05px;
      height: 112.05px;
      left: 203.59px;
      top: -86.41px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(209.3deg, #7b61ff -2.55%, #7b61ff 64.59%);
      filter: blur(60px);
    }
    #grad-3 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 136.28px;
      top: -21.72px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(
          209.3deg,
          rgba(242, 137, 41, 0) -2.55%,
          #f22959 64.59%
      );
      opacity: 0.7;
      filter: blur(60px);
    }
  }
  .connect-content:hover {
    p {

    }
    .plus {
      transform: rotate(180deg);
      background: white;
      margin-right: 3rem;
      div {
        background: black;
      }
    }
  }
  .connect-content:hover + .connect-grad {
    div {
      transform: scale(1);
    }
    #grad-2 {
      transform: rotate(165deg) scale(1);
    }
    #grad-3 {
      transform: rotate(165deg) scale(1);
    }
  }
}
</style>
