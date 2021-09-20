<template>
  <div class="pt-50 px-82.5 w-full flex flex-col slide">
    <div class="flex w-full justify-between blog-header">
      <h2 class="capitalize font-light text-4.5xl" style="color: #FF2E53">блог</h2>
      <img src="@/assets/images/volume.svg" class="w-10 h-10"  alt="">
    </div>
    <div class="posts-topics flex mt-16.25 mb-25">
      <p
        :class="{ active: activeTopic === 'all'}"
        @click="activeTopic = 'all'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border mr-7.5"
      >
        ВСЕ Статьи
      </p>
      <p
        :class="{ active: activeTopic === 'news'}"
        @click="activeTopic = 'news'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border mr-7.5"
      >
        НОВОСТИ
      </p>
      <p
        :class="{ active: activeTopic === 'technologies'}"
        @click="activeTopic = 'technologies'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border mr-7.5"
      >
        ТЕХНОЛОГИИ
      </p>
      <p
        :class="{ active: activeTopic === 'insights'}"
        @click="activeTopic = 'insights'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border mr-7.5"
      >
        INSIGHTS
      </p>
      <p
        :class="{ active: activeTopic === 'useful'}"
        @click="activeTopic = 'useful'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border mr-7.5"
      >
        ПОЛЕЗНОЕ
      </p>
      <p
        :class="{ active: activeTopic === 'different'}"
        @click="activeTopic = 'different'"
        class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border"
      >
        РАЗНОЕ
      </p>
    </div>
    <div class="posts flex flex-col">
      <postPreview/>
      <postPreview/>
      <postPreview/>
      <postPreview/>
      <postPreview/>
      <postPreview/>
      <postPreview/>
    </div>
    <div class="footer flex flex-col w-full mb-60">
      <div class="flex flex-col">
        <div class="become-client ml-41.5p ">
          <div class="connect-content flex justify-start items-center cursor-pointer w-max" @click="$emit('contact')">
            <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
              <div
                class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
              ></div>
              <div
                class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
              ></div>
            </div>
            <p class="uppercase font-semibold text-xxsm">ПОКАЗАТЬ ЕЩЕ 5 из 28 СТАТЕЙ</p>
          </div>

          <div class="connect-grad relative" style="z-index: -1">
            <div id="grad-1"></div>
            <div id="grad-2"></div>
            <div id="grad-3"></div>
          </div>
        </div>
      </div>
      <div class="flex justify-between mt-37">
        <p class="text-xxs font-medium" style="letter-spacing: 2px; color: rgba(110, 117, 141, 1)">
          © 2021 MAXFRAI AGENCY
        </p>
        <div class="h-px w-87.5" style="background:rgba(151, 163, 203, 0.3);"></div>
        <div class="w-5 h-px" style="background:rgba(151, 163, 203, 0);"></div>
      </div>
    </div>
  </div>
</template>

<script>
import postPreview from "./postPreview";

export default {
  name: "agencySlide1",
  data(){
    return{
      activeTopic:"all"
    }
  },
  components:{
    postPreview
  }
};
</script>

<style scoped>
.posts-topic.active{
  background: rgba(151, 163, 203, 0.5);
}
.posts-topic{
  border-color: rgba(151, 163, 203, 0.3);
  transition: all linear .2s;
}
</style>
