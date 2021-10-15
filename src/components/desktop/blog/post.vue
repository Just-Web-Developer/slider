<template>
  <div class="post relative overflow-scroll" id="post" @wheel.stop>
    <blogWrappers @blog="$emit('goBlog')" :post="true" @goHome="$emit('goHome')" @nav="$emit('nav')"/>
    <div  class="pt-50 pl-82.5 pr-50 w-full flex flex-col slide min-h-screen">
      <div class="header pr-32.5 flex">
        <div class="tags w-66 flex flex-col flex-shrink-0">
          <p class="posts-topic mb-2 cursor-pointer font-semibold text-xxsm uppercase w-max py-2 px-4 rounded-full border mr-4">
            новости
          </p>
        </div>

        <div class="flex flex-col">
          <div class="flex">
            <div class="title">
              <h2 class="font-light text-4.5xl" style="color: #FF2E53">{{ text.title }}</h2>
            </div>
            <div class="share w-66 flex-shrink-0 flex justify-end">
              <img src="@/assets/images/share.svg" class="w-12 h-12"  alt="">
            </div>
          </div>
          <div class="header-text pr-32.5 mt-12  mr-66">
            <p class="text-xxl text-white mb-12 font-medium">{{ text.text[0] }}</p>
            <p class="date font-medium text-xxs" style="letter-spacing: 0.3rem; color: #6E758D">
              {{ text.date }}
            </p>
          </div>
        </div>
      </div>
      <img class="flex pr-32.5 my-25" :src="require('@/assets/images/blog/' + id + '/first.png')" alt="">
      <div class="first-body pr-32.5 mx-66 mb-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">{{ text.subtitles[0] }}</h2>
        <p class="text-lg text-white mb-12 font-medium">{{ text.text[1] }}<br></p>
        <p class="text-lg text-white mb-12 font-medium">
          {{ text.text[2] }}<br></p>
        <p class="text-lg text-white mb-12 font-medium">{{ text.text[3] }}</p>
      </div>

      <doubleSlider :text="text" :id="id" :src="'blog'" class="mb-25"/>

      <div class="second-body pr-32.5 mx-66 mb-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">{{ text.subtitles[1] }}</h2>
        <p class="text-lg text-white mb-12 font-medium">{{ text.text[4].title }}<br></p>
        <ul class="text-lg text-white mb-12 font-medium list-disc pl-10">
          <li v-for="item in text.text[4].points" :key="item">{{ item }}</li>
          <br>
        </ul>
        <p class="text-lg text-white mb-12 font-medium">{{ text.text[5].title }}</p>
        <ol class="text-lg text-white mb-12 font-medium list-decimal pl-5">
          <li v-for="item in text.text[5].points" :key="item">{{ item }}</li>
        </ol>
        <p>{{ text.text[6][0] }}
          <br>
          {{ text.text[6][1] }}
        </p>
      </div>

      <div class="image pr-32.5 flex">
        <div class="signature w-66 justify-end mt-auto">
          <p class="w-55 font-medium text-base mr-10" style="color: #6e758d">
            {{ text.imgSource[0] }}
            <br>
            {{ text.imgSource[1] }}
          </p>
        </div>
        <img class="w-217.5 h-150" :src="require('@/assets/images/blog/' + id + '/second.png')" alt="">
      </div>

      <div class="third-body pr-32.5 mx-66 mt-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">{{ text.subtitles[2] }}</h2>
        <ul class="text-lg text-white mb-12 font-medium pl-5 list-disc">
          <li :class="{'mb-6': index < text.text[7].length - 1}" v-for="(item, index) in text.text[7]" :key="item">{{ item }}</li>
        </ul>
      </div>

      <a href="#post" class=" w-max to-top ml-66 mt-40 transform transition cursor-pointer">
        <svg width="14" class="transform transition duration-800 rotate-180" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
          <path d="M6.99998 0V12" stroke-linejoin="round"/>
        </svg>
        <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">{{ all.back }}</p>
      </a>

      <div class="next cursor-pointer w-315 relative " v-if="text.nextTitle">
        <!-- Background start -->
        <div class="absolute w-full h-full shadow z-10"></div>
        <img class="w-full" :src="require('@/assets/images/blog/' + id + '/next.png')" alt="">
        <div class="line absolute bottom-0 h-2"></div>
        <!-- Background end -->
        <div class="content absolute z-20 bottom-23 left-10">
          <p class="next-post-title text-xxsm uppercase font-semibold mb-6">{{ all.next }}</p>
          <h3 class="w-110 text-3.55xl">{{ text.nextTitle }}</h3>
        </div>
      </div>
    </div>
  </div>

</template>

<script>
import doubleSlider from "../doubleSlider"
import blogWrappers from "./blogWrappers";

export default {
  name: "post",
  emits:['goHome', 'goBlog', 'nav'],
  props:["id"],
  components:{
    doubleSlider,
    blogWrappers
  },
  computed:{
    text(){
      return require("@/assets/text/blog/posts/ru.json").posts[this.id]
    },
    all(){
      return require("@/assets/text/blog/posts/ru.json")
    }
  }
};
</script>

<style lang="scss" scoped>

// Next post start
.next{
  margin-top: 9rem;
  overflow: hidden;
  height: 18.75rem;
  transition: all linear .3s;
  .line{
    transition: all linear .3s;
    background: #FF2E53;
    width: 0;
    z-index: 11;
  }
  img.w-full{
    transition: all linear .3s;
  }
  .shadow{
    transition: all linear .3s;
    background: rgba(0,0,0,.8);
  }
}
.next:hover{
  //margin-top: 7.125rem;
  //height: 20.625rem;
  .line{
    width: 100%;
  }
  img.w-full{
    transform: scale(1.15);
  }
  .shadow{
    background: rgba(0,0,0,.4);
  }
}
// Next post end

//Back to top button start
.to-top{
  svg{
    path{
      transition: all linear .3s;
      stroke: rgba(151, 163, 203, 0.6);
    }
  }
  p{
    transition: all linear .3s;
    color: rgba(151, 163, 203, 0.6);
  }
}
.to-top:hover{
  svg{
    path{
      transition: all linear .3s;
      stroke: white;
    }
  }
  p{
    transition: all linear .3s;
    color: white;
  }
}
//Back to top button end

</style>
