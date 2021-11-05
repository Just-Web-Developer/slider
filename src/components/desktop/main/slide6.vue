<template>
  <div id="slide-6" class="slide ml-83 pt-50 h-screen relative flex h-125">
    <div class="blog-left w-46.75">
      <img src="@/assets/images/volume.svg" class="w-10 h-10 mt-17"  alt="">
    </div>
    <div class="blog-right flex flex-col">
      <p
        class=" uppercase fz-10 font-medium mb-15 ml-21.25"
        style="color: rgba(110, 117, 141, 1); letter-spacing: 2px">
        {{ text.blogName }}
      </p>
      <div class="blog-container w-271.5 h-114 flex" :class="{'pl-21.25': !hover}">
        <div v-for="(item, index) in text.news" :key="item" class="news w-55" @mouseover="hoverStart(index)" @mouseleave="hoverEnd" :class="{
          'ml-0 mr-10': index !== text.news.length-1 && !hover,
          'mr-5': index !== text.news.length-1 && hover && index !== hoverIndex && index + 1 !== hoverIndex ,
          'mr-20 w-76.25': index === hoverIndex && index === 0 && hover,
          'mr-0 ml-20 w-76.25': index === hoverIndex && index === text.news.length-1 && hover,
          'mx-12.5 w-76.25': index === hoverIndex && index > 0 && index < text.news.length-1 && hover
        }" >
          <div class="relative">
            <transition name="text">
              <p v-if="index !== hoverIndex" class="w-55 fz-16 absolute top-0 left-0 mb-6 h-38 font-medium unactive ">
                {{item.text}}
              </p>
            </transition>
            <p class="mb-6 h-38 opacity-0" :class="{'w-full font-normal text-white fz-18': index === hoverIndex && hover, 'w-55 fz-16 font-medium unactive': index !== hoverIndex }" style="">
              {{item.text}}
            </p>
            <transition name="text">
              <p v-if="index === hoverIndex && hover" class="absolute left-0 top-0 w-76.25 font-normal text-white fz-18">{{item.text}}</p>
            </transition>
          </div>

          <div class="overflow-hidden relative pb-10" :class="{'w-76.25 h-70': index === hoverIndex && hover, 'w-42.5 h-42.5': index !== hoverIndex }">
            <img :src="require('@/assets/images/slide_6/'+ item.image + '.png')" :class="{'w-76.25 h-60 image-casual': index === hoverIndex && hover, 'w-42.5 h-42.5 image-dark': index !== hoverIndex }" :style="'transform-origin:'+item.pos+';transform: scale('+(index === hoverIndex && hover ? 1 : item.scale)+');'" alt="">
            <img class="absolute w-5 h-5 bottom-0  cursor-pointer link-arrow" :class="{'left-0 opacity-100': index === hoverIndex && hover, 'left-4 opacity-0': index !== hoverIndex }" src="@/assets/images/slide_6/arrow.svg" alt="">
          </div>

        </div>
      </div>
      <div class="mt-10.5 ml-auto flex items-center all-news cursor-pointer">
        <p class="text-right font-medium fz-14 uppercase mr-4">{{ text.all }}</p>
        <img src="@/assets/images/cross.svg" class="w-14 h-14  p-4 rounded-full border-2 " alt="">
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide6",
  data(){
    return{
      hover: false,
      hoverIndex: null
    }
  },
  props:['lang'],
  methods:{
    hoverStart(index){
      this.hover = true
      this.hoverIndex = index
    },
    hoverEnd(){
      this.hover = false
      this.hoverIndex = null
    }
  },
  computed:{
    text(){
      return require("@/assets/text/main/slide6/ru.json")
    }
  }
};
</script>

<style lang="scss" scoped>

.text-enter-active,
.text-leave-active,
.all-news img,
.all-news p,
.blog-container,
.news,
.news *{
  transition: all .3s linear;
}

.text-enter-from,
.text-leave-to{
  opacity: 0;
}

.news p.unactive {
  color:rgba(110, 117, 141, 1);
}
.link-arrow:hover{
  left: 0.5rem;
}

.all-news{
  img{
    border-color:rgba(151, 163, 203, 0.3)
  }
  p{
    opacity: 0;
    transform: translateX(50%);
  }
}

.all-news:hover{
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
.image-dark{
  filter: brightness(50%);
}
.image-casual{
  filter: brightness(100%);
}
</style>
