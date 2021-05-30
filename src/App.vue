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
    <div id="slide-2" class="slide ml-83 mt-23.5 pt-27.5 h-screen relative flex" style="height: max-content">
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
          <div v-for="(stackSlide, index) in data.stackSlider" :key="index.id" >
            <transition :name="slide2.stackDirection" v-if="index < 5">
              <div class="flex stack-slide absolute h-1/3 items-center"  :class="index === 0 ? 'first' : index === 1 ? 'second': index===2 ? 'third' :  index===3 ? 'fourth' : index===4 ? 'fifth' : ''"  >
                <img :src="require('./assets/images/slide_2/stack/'+stackSlide.image+'.svg')" class="h-19 w-19 p-4 rounded-full" style="background:rgba(110, 117, 141, .2);" alt="">
                <p class="text-base font-medium ml-5" style="line-height: 1.5rem">{{stackSlide.text}} {{index}}</p>
              </div>
            </transition>
          </div>
        </div>
        <div class="mt-auto flex">
          <img class="stack-arrow cursor-pointer transform rotate-90 p-2.5 rounded-full w-10 h-10" @click="stackPrev()" src="./assets/images/slide_2/stack/arrow.svg" alt="">
          <img class="stack-arrow cursor-pointer transform -rotate-90 p-2.5 rounded-full ml-4 w-10 h-10" @click="stackNext()" src="./assets/images/slide_2/stack/arrow.svg" alt="">
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
        stackDirection:"stack-up"
      },
      data:{
        "stackSlider":[
          {"image":"send", "text": "Телеграм-боты"},
          {"image":"enter", "text": "Cистема входа, учета сотрудников по заданным параметрам"},
          {"image":"layout", "text": "Готовые решения для сайтов: магазины, новостные ресурсы"},
          {"image":"send", "text": "Телеграм-боты"},
          {"image":"enter", "text": "Cистема входа, учета сотрудников по заданным параметрам"},
          {"image":"layout", "text": "Готовые решения для сайтов: магазины, новостные ресурсы"},

        ]
      }
    }
  },
  methods:{
    nextSlide(){
      if (this.slide <= this.max){
        this.slide++
      }
      else{
        this.slide = 1
      }
    },
    prevSlide(){
      if (this.slide !== 1){
        this.slide--
      }
    },
    stackNext(){
      this.slide2.stackDirection = "stack-up"
      this.data.stackSlider.push(this.data.stackSlider.shift())

    },
    stackPrev(){
      this.slide2.stackDirection = "stack-down"
      this.data.stackSlider.unshift(this.data.stackSlider.pop())

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

.stack-up-screen-enter-active,
.stack-up-screen-leave-active,
.stack-down-screen-enter-active,
.stack-down-screen-leave-active,
.stack-slide{
  position: absolute;
  top: 0;
  transition: all 1s linear;
}

.stack-up-enter-from,
.stack-down-leave-to {
  transform: translateY(100%);

}
.stack-down-enter-from,
.stack-up-leave-to {
  transform: translateY(-100%);
}

.stack-slider{
  .first{
    top: -33.3%;
  }
  .second{
    top: 0;
  }
  .third{
    top: 33.3%;
  }

  .fourth{
    top: 66.6%;
  }

  .fifth{
    top: 100%;
  }
}




.stack-arrow{
  transition: all linear 0.3s;
  &:hover{
    background: white;
  }
}
</style>
