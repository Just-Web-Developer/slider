<template>
  <div id="slide-4" class="slide ml-83 pt-52 h-screen relative flex h-125">
    <div class="works-left w-48p flex flex-col">
      <p
        class="ml-auto text-center mb-15 uppercase text-xxs font-medium"
        style="color: rgba(110, 117, 141, 1); letter-spacing: 2px"
      >
        projects
      </p>
      <div class="works-content flex pl-15 relative">
        <div v-for="(item, index) in works" :key="item+index" class="absolute left-0" >
          <transition :name="slideDirection + '-count'">
            <p
              v-if="index === currsentSlide"
              class="uppercase text-xxs font-medium"
              style="color: rgba(151, 163, 203, 0.6)"
            >
              0{{ currsentSlide + 1 }}
            </p>
          </transition>
        </div>


        <div class="work overflow-hidden relative w-full h-125" @mouseover="hover = true" @mouseleave="hover = false" :class="{'hover': hover}" >
            <div v-for="(work, index) in works" :key="work+index" >
              <transition :name="slideDirection">
                <div class="absolute w-full h-125 " v-if="index === currsentSlide">
                  <div class="relative w-full h-125">
                    <img  :src="require('../assets/images/slide_4/'+ work.image + '.png')" class="absolute left-0 top-0 right-0 h-125 slide" alt="" />
                    <img src="../assets/images/eye-circle.svg" class="w-12 h-12 absolute left-10 bottom-10 z-20 cursor-pointer" :class="index"  alt="">
                    <img src="../assets/images/arrow-down-circle.svg" class="w-12 h-12 absolute  bottom-10 cursor-pointer" :class="hover ? 'left-24' : 'left-10'" alt="">
                  </div>
                </div>
              </transition>

            </div>
        </div>
      </div>
    </div>
    <div class="works-right ml-40 mt-18 w-87.5 h-125 flex flex-col">
      <div class="work-description cursor-pointer relative mb-6" v-for="(item, index) in works" @click="changeSlide(index)"  :class="{'active': index === currsentSlide}" :key="item+index">
        <h4 class="company-name text-base font-medium uppercase text-right " :class="{
          'text-3.5xl font-normal mb-5': index === currsentSlide
        }">{{item.name}}</h4>
        <transition name="text">
          <p v-if="index === currsentSlide" class="company-description text-right font-medium text-base">{{item.description}}</p>
        </transition>
      </div>
      <div class="mt-auto ml-auto flex items-center projects cursor-pointer">
        <p class="text-right font-medium text-sm uppercase mr-4">все проекты</p>
        <img src="../assets/images/cross.svg" class="w-14 h-14  p-4 rounded-full border-2 " alt="">
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "slide4",
  data(){
    return{
      slideDirection: '',
      hover:false,
      currsentSlide:0,
      works:[
        {
          image:"atlas",
          name:"Atlas Weekend",
          description:"Разработка и техническая поддержка всех систем управления фестивалем"
        },
        {
          image:"playboy",
          name:"Playboy Ukraine",
          description:"Стратегия продвижения и развития бренда: от сайта до социальных сетей"
        },
        {
          image:"the_world_news",
          name:"The World News",
          description:"Разработка и запуск уникальной платформы международного информационного агентства на технологии блокчейн"
        },
        {
          image:"music_awards",
          name:"M1 Music Awards",
          description:"Разработка и поддержка системы контроля входа при большом потоке гостей"
        },
        {
          image:"unn",
          name:"UNN",
          description:"Поддержка, доработка, развитие и SEO-оптимизация новостного портала с уникальными техническими решениями"
        },
        {
          image:"sluhay",
          name:"Слухай",
          description:"Разработка идеи и непосредственно самой платформы для аудиокниг на украинском языке"
        }
      ]
    }
  },
  methods:{
    changeSlide(index){
      if (index > this.currsentSlide){
        this.slideDirection = "next-slide"
      }
      if (index < this.currsentSlide){
        this.slideDirection = "prev-slide"
      }
      this.currsentSlide = index
    }
  }
};
</script>

<style lang="scss" scoped>
.company-name{
  color: rgba(110, 117, 141, 1);

}
.active .company-name{
  color:rgba(255, 46, 83, 1);
}

.work img.slide{
  transform: translateX(0) scale(1.05);
  filter: brightness(70%);
}
.work.hover img.slide{
  transform: translateX(0) scale(1);
  filter: brightness(115%);
}

.work img{
  transition: all ease-in .3s;
}

.work-description,
.company-name,
.work .next-slide-enter-active,
.work .next-slide-leave-active,
.work .prev-slide-enter-active,
.work .prev-slide-leave-active,
.next-slide-count-enter-active,
.next-slide-count-leave-active,
.prev-slide-count-enter-active,
.prev-slide-count-leave-active,
.text-enter-active,
.text-leave-active{
  transition: all .6s ease-in;
}


.work .next-slide-enter-from,
.work .prev-slide-leave-to {
  transform: translateX(101%) ;
}
.work .prev-slide-enter-from,
.work .next-slide-leave-to {
  transform: translateX(-101%) ;
}

.next-slide-count-enter-from,
.prev-slide-count-leave-to,
.prev-slide-count-enter-from,
.next-slide-count-leave-to{
  opacity: 0;
}


.text-enter-from,
.text-leave-to{
  opacity: 0;
  line-height: 0px;
  transform: translateY(40%);
}
.projects{
  img, p {
    transition: all .3s linear;
  }
  img{
    border-color:rgba(151, 163, 203, 0.3)
  }
  p{
    opacity: 0;
    transform: translateX(50%);
  }
}

.projects:hover{
  img{
    transform: rotate(-180deg);
    border-color: white;
    background: white;
  }
  p{
    transform: translateX(0);
    opacity: 1;
  }
}


</style>
