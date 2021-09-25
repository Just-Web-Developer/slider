<template>
  <div class="post relative overflow-scroll" id="post" @wheel.stop>
    <blogWrappers @blog="$emit('goBlog')" :post="true" @goHome="$emit('goHome')" @nav="$emit('nav')"/>
    <div  class="pt-50 pl-82.5 pr-50 w-full flex flex-col slide min-h-screen">
      <div class="header pr-32.5 flex">
        <div class="tags w-66 flex-shrink-0">
          <p class="posts-topic cursor-pointer font-semibold text-xxsm uppercase w-max py-2 px-4 rounded-full border mr-4">
            новости
          </p>
        </div>
        <div class="title">
          <h2 class="font-light text-4.5xl" style="color: #FF2E53">My trip to Japan, an epiphany to accessibility and socially inclusive design</h2>
        </div>
        <div class="share w-66 flex-shrink-0 flex justify-end">
          <img src="@/assets/images/share.svg" class="w-12 h-12"  alt="">
        </div>
      </div>
      <div class="header-text pr-32.5 mt-12  mx-66">
        <p class="text-xxl text-white mb-12 font-medium">One of the biggest challenges today — from a global and business point of view — is to design for a more sustainable and socially inclusive world. While we have new products and services raining everyday into our world, only some notable ones excel in providing delightful experiences.</p>
        <p class="date font-medium text-xxs" style="letter-spacing: 0.3rem; color: #6E758D">
          01.04.2021
        </p>
      </div>
      <img class="flex pr-32.5 my-25" src="@/assets/images/blog/01/first.png" alt="">
      <div class="first-body pr-32.5 mx-66 mb-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">Information designed for ease of access and social inclusivity</h2>
        <p class="text-lg text-white mb-12 font-medium">Catching a train during peak hours at Tokyo station is highly challenging, with a 200% increase in congestion ratio in most of the commuter lines; waves of people rushing for work moving in all directions is a common sight. To commute by trains, one needs either a JR pass, or IC prepaid cards that can be recharged for a short change in any train/bus station eg. ICOCA, SUICA , etc.<br></p>
        <p class="text-lg text-white mb-12 font-medium">
          A noticeable effort has been made in major Japanese cities to ensure that every train, metro, tram or bus is quickly accessible for all types of users — visually impaired, wheel-chair users, mothers with young infants and colour blind users, to name some. The train system is very complex, but they have been colour coded everywhere. No matter which station you are in, you just need to find the right colour code and the platform in order to go to the next station. There are also sign boards indicating which side of the platform you need to stand on, earmarking the direction of the arriving train.<br></p>
        <p class="text-lg text-white mb-12 font-medium">
          Below is an image of a colour coded wall paneling that helps passengers inside the Tokyo Metro Fukutoshin Line’s Shibuya Station to navigate passages to connecting rail lines. Shibuya is the fourth busiest station on the Tokyo Metro network.</p>
      </div>
      <doubleSlider :text="text" :src="'blog'" class="mb-25"/>
      <div class="second-body pr-32.5 mx-66 mb-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">Highly efficient public transports & systems for all types of users</h2>
        <p class="text-lg text-white mb-12 font-medium">As per my understanding, to get a ticket at any fare gate at any station, the mechanism is as follows:<br></p>
        <ul class="text-lg text-white mb-12 font-medium list-disc pl-10">
          <li>Tap the prepaid IC card.</li>
          <li>Balance will be displayed and checked.</li>
          <li>Wait for the gates to open.</li>
          <br>
        </ul>
        <p class="text-lg text-white mb-12 font-medium">But in Japan, this task is slightly modified for efficiency. In order to keep the crowd moving faster the steps are interchanged:</p>
        <ol class="text-lg text-white mb-12 font-medium list-decimal pl-5">
          <li>Tap the prepaid IC card — using multiple tap access.</li>
          <li>Gates will open.</li>
          <li>The balance will be displayed.</li>
        </ol>
        <p>By a simple reordering of the same task, people are able to move much more freely and without breaking a step.
          <br>
          Fare gates accommodate a wide variety of users. Note that the gate assembly is long enough so that exiting passengers do not have to slow or stop walking in order for the gate to open. The gate has multiple smart card targets to speed fare collection.
        </p>
      </div>
      <div class="image pr-32.5 flex">
        <div class="signature w-66 justify-end mt-auto">
          <p class="w-55 font-medium text-base mr-10" style="color: #6e758d">
            Image source: Wikipedia |
            <br>
            CC BY-SA 3.0
          </p>
        </div>
        <img class="w-217.5 h-150" src="@/assets/images/blog/01/second.png" alt="">
      </div>
      <div class="third-body pr-32.5 mx-66 mt-25">
        <h2 class="text-3.55xl mb-12" style="color: #FF2E53">Key take-aways are</h2>
        <ul class="text-lg text-white mb-12 font-medium pl-5 list-disc">
          <li class="mb-6">In Japan, everybody is a user! There is no average / normal / typical user as per our design process - this only made me question the idea of personas in design, which tends to unconsciously leave out certain user segments who can use the product.</li>
          <li class="mb-6">Inclusive design means making your product accessible to as many users as possible. This can be done by just listening to people, observing the struggles they face during commute, and identifying the barriers to performing seemingly simple tasks.</li>
          <li class="mb-6">Designing with accessibility at the forefront is a cross functional team effort. I am certain that accessibility was considered as a key principle at the early stages of planning and implementation, as opposed to being an after thought in the process!</li>
          <li class="mb-6">When a designed product has made considerations for user behavior and encompasses smaller details into it, the changes can result in brilliant experiences.</li>
          <li>It’s the concept of Kaizen — to strive for continuous improvement which reflects in almost every designed environment in Japan.</li>
        </ul>
      </div>
      <a href="#post" class=" w-max to-top ml-66 mt-40 transform transition cursor-pointer">
        <svg width="14" class="transform transition duration-800 rotate-180" height="13" viewBox="0 0 14 13" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1 6L7 12L13 6" stroke-linejoin="round"/>
          <path d="M6.99998 0V12" stroke-linejoin="round"/>
        </svg>
        <p class="text-xxs font-medium uppercase mt-2.5" style="letter-spacing: 0.3em">back to top</p>
      </a>
      <div class="next cursor-pointer w-315 relative ">
        <!-- Background start -->
        <div class="absolute w-full h-full shadow z-10"></div>
        <img class="w-full" src="@/assets/images/blog/01/next.png" alt="">
        <div class="line absolute bottom-0 h-2"></div>
        <!-- Background end -->
        <div class="content absolute z-20 bottom-23 left-10">
          <p class="next-post-title text-xxsm uppercase font-semibold mb-6">СЛЕДУЮЩая статья</p>
          <h3 class="w-110 text-3.55xl">Graphic Design Trends 2021 Inspired By What We All Experienced This Year</h3>
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
  components:{
    doubleSlider,
    blogWrappers
  },
  data(){
    return{
      text:{
        images: ['01','02','03','04']
      }
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
