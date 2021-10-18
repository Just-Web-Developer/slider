<template>
  <projectWrapper @projects="$emit('projects')" @nav="$emit('nav')"/>
  <div id="project" class="pt-50 pl-82.5 pr-50 w-full flex flex-col slide min-h-screen">
    <div class="header pr-32.5 flex">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-4.5xl" style="color: #FF2E53">{{ text.titleM }}</h2>
        <a href="#project" class=" w-max to-top transform transition cursor-pointer" >
          <svg width="14"  height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
            <path d="M6.99998 0V12" stroke-linejoin="round"/>
          </svg>
          <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">scroll</p>
        </a>
      </div>
      <div class="right flex flex-col">
        <div class="top flex">
          <div class="top-left flex flex-col w-120 mr-10">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-10">
              <p class="uppercase font-medium text-xs mb-5" style="color:#6E758D;">{{ text.taskTitle }}</p>
              <p class="text-base font-medium w-87.5">{{ text.title }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
          <div class="top-right flex flex-col w-55">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content mt-5 mb-10">
              <p class="uppercase font-medium text-xs mb-5 w-38" style="color:#6E758D;">{{ text.realizationTimeTitle }}</p>
              <p class="text-5.5xl">{{ text.realizationTime }}</p>
            </div>
            <div class="line w-full mt-auto h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
        </div>
        <p class="mt-37.5 text-xxl font-medium">{{ text.text[0] }}</p>
      </div>

    </div>
    <img :src="require('@/assets/images/projects/' + id + '/first.png')" alt="" class="first-image pr-32.5 mt-50">

    <p class="prolog pr-32.5 mt-50 ml-130.7 font-medium text-xxl">{{ text.text[1] }}</p>

    <div class="problems pr-32.5 flex mt-37.5">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-3.55xl w-87.5" style="color: #FF2E53">{{ text.problemsTitle }}</h2>

      </div>
      <div class="right flex flex-col">
        <div class="top flex">
          <div class="top-left flex flex-col w-87.5 mr-10">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">01</h6>
              <p class="text-base font-medium w-80">{{ text.problems[0] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">03</h6>
              <p class="text-base font-medium w-80">{{ text.problems[2] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
          <div class="top-right flex flex-col w-87.5">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">02</h6>
              <p class="text-base font-medium w-80 h-12">{{ text.problems[1] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">04</h6>
              <p class="text-base font-medium w-80">{{ text.problems[3] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
        </div>
      </div>

    </div>

    <doubleSlider :text="text" :src="'projects'" :id="id" class="mt-65 mb-50"/>

    <div class="result pr-32.5 flex mt-37.5">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-3.55xl w-87.5" style="color: #FF2E53">{{ text.resultTitle}}</h2>

      </div>
      <div class="right flex flex-col">
        <div class="top flex">
          <div class="top-left flex flex-col w-87.5 mr-10">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">01</h6>
              <p class="text-base font-medium w-80 h-18.75">{{ text.result[0] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">03</h6>
              <p class="text-base font-medium w-80 h-25">{{ text.result[2] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">05</h6>
              <p class="text-base font-medium w-80 h-25">{{ text.result[4] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>


          <div class="top-right flex flex-col w-87.5">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">02</h6>
              <p class="text-base font-medium w-80 h-18.75">{{ text.result[1] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">04</h6>
              <p class="text-base font-medium w-80 h-25">{{ text.result[3] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">06</h6>
              <p class="text-base font-medium w-80 h-25">{{ text.result[5] }}</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
        </div>
      </div>

    </div>

    <div class=" w-max to-top ml-130.7 mt-40 transform transition cursor-pointer" >
      <svg width="14" class="transform transition duration-800 rotate-180" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
        <path d="M6.99998 0V12" stroke-linejoin="round"/>
      </svg>
      <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">back to top</p>
    </div>
    <div class="next w-315 cursor-pointer relative" v-if="text.nextTitle && text.nextImage">
      <!-- Background start -->
      <div class="absolute w-full h-full shadow z-10"></div>
      <img class="w-full" :src="require('@/assets/images/projects/' + text.id + '/next.png')" alt="">
      <div class="line absolute bottom-0 h-2"></div>
      <!-- Background end -->
      <div class="content absolute z-20 bottom-23 left-10">
        <p class="next-post-title text-xxsm uppercase font-semibold mb-6">{{ text.next }}</p>
        <h3 class="w-110 text-3.55xl">{{text.nextTitle}}</h3>
      </div>
    </div>
  </div>
</template>

<script>
import projectWrapper from "./projectWrapper";
import doubleSlider from "../../doubleSlider";

export default {
  name: "project",
  components:{
    projectWrapper,
    doubleSlider
  },
  computed:{
    text(){
      return require('@/assets/text/project/ru.json').projects[this.id]
    }
  },
  props:['id', "lang"],
  emits:['projects', 'nav']
};
</script>

<style scoped lang="scss">


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