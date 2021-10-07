<template>
  <div class="pt-50 pl-82.5 flex slide ">
    <div class="slide-content flex h-max" @mouseover="hover = true" @mouseleave="hover = false">
      <div class="left flex flex-col ">
        <div class="relative h-37.5">
          <div v-for="(item, index) in text.works" :key="item+index" class="absolute left-0" >
            <transition name="slide">
              <p
                v-if="index === currentSlide"
                class="uppercase text-xxs font-medium"
                style="color: rgba(151, 163, 203, 0.6)"
              >
                0{{ currentSlide + 1 }}
              </p>
            </transition>
          </div>
        </div>
        <div class="relative w-130 h-112.5 flex hover">
          <transition-group name="text">
            <div class="text absolute" v-for="(item, index) in text.works" v-show="index === currentSlide" :key="item.name + index">
              <h4 class="company-name text-3.5xl font-normal mb-5" style="color:rgba(255, 46, 83, 1);">
                {{ item.name }}
              </h4>
              <p class="company-description font-medium text-base">
                {{ item.description }}
              </p>
            </div>
          </transition-group>
          <img src="@/assets/images/eye-circle.svg" class="w-12 h-12 links absolute left-0 bottom-0 z-20 cursor-pointer"  alt="">
          <img src="@/assets/images/arrow-down-circle.svg" class="w-12 h-12 links absolute  bottom-0 cursor-pointer" :class="hover ? 'left-16' : 'left-0'" alt="">
        </div>


      </div>
      <div class="right h-150 w-217.5 relative overflow-hidden">
          <div class=" absolute work left-0" v-for="(item, index) in text.works" :key="item.name + index">
            <div class="relative h-150 w-217.5">
              <transition name="image">
                <img class="h-150 w-217.5 absolute work left-0" :class=" {'hover': hover}"   v-if="index === currentSlide"  :src="require('@/assets/images/slide_4/'+ item.image + '.png')" alt="">
              </transition>
            </div>
          </div>

      </div>
    </div>

  </div>
</template>

<script>
export default {
  name: "projectsSlide2",
  props:{
    currentSlide:{
      type: Number,
      default(){
        return 0
      }
    }
  },
  computed:{
    text(){
      return require("@/assets/text/projects/slide2/ru.json")
    }
  },
  data(){
    return{
      hover:false,
    }
  }
};
</script>

<style scoped>
.text-enter-active,
.text-leave-active,
.slide-enter-active,
.slide-leave-active{
  transition: all linear .5s;
  top: 0;
}
.text-enter-from{
  top: 40%;
  opacity: 0;
}
.text-leave-to{
  top: -40%;
  opacity: 0;
}
.slide-enter-from{
  opacity: 0;
}
.slide-leave-to{
  opacity: 0;
}



.links{
  transition: all linear .2s;
}
.work{
  transition: all linear .2s;
  transform: translateX(0) scale(1);
}
.work.hover{
  transform: scale(1.1);
}

.image-leave-active,
.image-enter-active{
  transition: all linear .5s;
}

.image-enter-from {
  left: 100%;
}
.image-leave-to{
  left: -100%;
}
</style>