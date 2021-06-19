<template>
  <div id="slide-4" class="slide ml-83 mt-27.5 h-screen relative flex h-125">
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
                <img v-if="index === currsentSlide"  :src="require('../assets/images/slide_4/'+ work.image + '.png')" class="absolute left-0 top-0 right-0 h-125 slide" alt="" />
              </transition>
              <transition :name="slideDirection + '-see'">
                <div class="">
                  <img src="../assets/images/eye-circle.svg" class="w-12 h-12 absolute left-10 bottom-10 z-20 cursor-pointer" v-if="index === currsentSlide" alt="">
                  <img src="../assets/images/arrow-down-circle.svg" class="w-12 h-12 absolute  bottom-10 cursor-pointer" v-if="index === currsentSlide" :class="hover ? 'left-24' : 'left-10'" alt="">
                </div>
              </transition>
            </div>
        </div>
      </div>
    </div>
    <div class="works-right ml-40 w-87.5 flex flex-col">
      <div class="work-description cursor-pointer relative mb-6" v-for="(item, index) in works" @click="changeSlide(index)"  :class="{'active': index === currsentSlide}" :key="item+index">
        <h4 class="company-name text-base font-medium uppercase text-right " :class="{
          'text-3.5xl font-normal mb-5': index === currsentSlide
        }">{{item.name}}</h4>
        <transition name="text">
          <p v-if="index === currsentSlide" class="company-description text-right">{{item.description}}</p>
        </transition>

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


.work-description,
.company-name,
.company-description,
.next-slide-enter-active,
.next-slide-leave-active,
.prev-slide-enter-active,
.prev-slide-leave-active,
.next-slide-count-enter-active,
.next-slide-count-leave-active,
.prev-slide-count-enter-active,
.prev-slide-count-leave-active,
.text-enter-active,
.text-leave-active,
.next-slide-see-enter-active,
.next-slide-see-leave-active
.prev-slide-see-enter-active,
.prev-slide-see-leave-active{
  transition: all .6s ease-in;
}

.next-slide-enter-from,
.prev-slide-leave-to {
  transform: translateX(101%);
}
.prev-slide-enter-from,
.next-slide-leave-to {
  transform: translateX(-101%);
}

.next-slide-count-enter-from,
.prev-slide-count-to,
.prev-slide-count-enter-from,
.next-slide-count-leave-to{
  opacity: 0;
}

.prev-slide-see-enter-active,
.next-slide-see-leave-active{
  left: calc(-100% + 2.5rem);
}
.next-slide-see-enter-active,
.prev-slide-see-leave-active{
  left: calc(100% + 2.5rem);
}

.text-enter-from,
.text-leave-to{
  opacity: 0;
  line-height: 0;
  transform: translateY(40%);
}
.see-enter-from,
.see-leave-to{
  opacity: 0;
  line-height: 0;
  transform: translateY(40%);
}

.work img{
  transition: all linear .3s;
}

.work img.slide{
  transform: scale(1.05);
  filter: brightness(70%);
}
.work.hover img.slide{
  transform: scale(1);
  filter: brightness(115%);
}
</style>
