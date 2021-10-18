<template>
  <div id="slide-5" class="slide ml-83 pt-50 h-screen relative flex h-125">
    <div class="about-left w-47.8p flex flex-col">
      <div class="flex justify-between">
        <img src="@/assets/images/talk.svg" class="w-9 h-9" alt="">
        <p
          class="text-center uppercase text-xxs font-medium"
          style="color: rgba(110, 117, 141, 1); letter-spacing: 2px">
          {{ text.agencyName }}
        </p>
      </div>
      <p class="text-xxl font-medium text-justify text mt-17">{{ text.text }}</p>
      <div class="mt-37.5 flex items-center agency cursor-pointer">
        <img src="@/assets/images/cross.svg" class="w-14 h-14  p-4 rounded-full border-2 " alt="">
        <p class="text-right font-medium text-sm uppercase ml-4">{{ text.agency }}</p>
      </div>
    </div>
    <div class="about-right ml-42 pt-27.5 w-87.5 overflow-hidden flex flex-col">
      <div class="flex items-center links cursor-pointer">
        <img src="@/assets/images/wiki.svg" class="w-14 h-14  p-4 rounded-full border-2 " alt="">
        <p class="text-right font-medium text-sm uppercase ml-4">{{ text.wikipedia }}</p>
      </div>
      <div class="flex items-center mb-25 mt-5 links cursor-pointer">
        <img src="@/assets/images/fb.svg" class="w-14 h-14  p-4 rounded-full border-2 " alt="">
        <p class="text-right font-medium text-sm uppercase ml-4">{{ text.facebook }}</p>
      </div>
      <div class="overflow-hidden mb-8" @mouseover="maxHover = true" @mouseleave="maxHover = false">
        <img src="@/assets/images/slide_5/max_photo.png" class="w-87.5  max" alt="">
      </div>
      <div class="barcode flex" :class="{'active': maxHover}">
        <div id="block-1"></div>
        <div id="block-2"></div>
        <div id="block-3"></div>
        <div id="block-4"></div>
        <div id="block-5"></div>
        <div id="block-6"></div>
        <div id="block-7"></div>
        <div id="block-8"></div>
        <div id="block-9"></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide5",
  data(){
    return{
      maxHover:false
    }
  },
  props:['lang'],
  computed:{
    text(){
      return require("@/assets/text/main/slide5/ru.json")
    }
  },
};
</script>

<style lang="scss" scoped>
.text{
  text-indent: 17rem;
}

.agency{
  width: max-content;
  img, p {
    transition: all .3s linear;
  }
  img{
    border-color:rgba(151, 163, 203, 0.3)
  }
  p{
    opacity: 0;
    transform: translateX(-50%);
  }
}

.agency:hover{
  img{
    transform: rotate(180deg);
    border-color: white;
    background: white;
  }
  p{
    transform: translateX(0);
    opacity: 1;
  }
}

.links{
  width: max-content;
  img, p {
    transition: all .3s linear;
  }
  img{
    border-color:rgba(151, 163, 203, 0.3)
  }
  p{
    opacity: 0;
    transform: translateX(-50%);
  }
}

.links:hover{
  img{
    border-color: white;
    background: white;
  }
  p{
    transform: translateX(0);
    opacity: 1;
  }
}
.max{
  transition: all linear .3s;
  transform-origin: left bottom;
  transform: scale(1.4);
  filter: brightness(50%);
}

.max:hover{
  transform: scale(1);
  filter: brightness(100%);
}

.barcode{
  div{
    transition: all linear .3s;
    background: rgba(151, 163, 203, 0.3);
    height: 10px;
    margin-right: 5px;
  }
  #block-1{
    width: 9px;
  }
  #block-2{
    width: 3px;
  }
  #block-3{
    width: 1px;
  }
  #block-4{
    width: 7px;
  }
  #block-5{
    width: 3px;
  }
  #block-6{
    width: 8px;
  }
  #block-7{
    width: 1px;
  }
  #block-8{
    width: 1px;
  }
  #block-9{
    width: 3px;
  }
}
.barcode.active{
  div{
    margin-right: 7px;
  }
  #block-1{
    width: 4px;
  }
  #block-2{
    width: 9px;
  }
  #block-3{
    width: 1px;
  }
  #block-4{
    width: 3px;
  }
  #block-5{
    width: 8px;
  }
  #block-6{
    width: 2px;
  }
  #block-7{
    width: 4px;
  }
  #block-8{
    width: 1px;
  }
  #block-9{
    width: 30px;
  }
}
</style>
