<template>
  <div class="pt-50 px-82.5 w-full flex flex-col slide">
    <div class="flex w-full justify-between blog-header">
      <h2 class="capitalize font-light fz-45" style="color: #FF2E53">{{ text.blog }}</h2>
      <img src="@/assets/images/volume.svg" class="w-10 h-10"  alt="">
    </div>
    <div class="posts-topics flex mt-16.25 mb-25">
      <p
        v-for="(item, index) in text.tags"
        :key="item[0]"
        :class="{ active: activeTopic === item[0], 'mr-7.5': index < text.tags.length - 1}"
        @click="setTopic(item[0])"
        class="posts-topic cursor-pointer font-semibold fz-13 uppercase py-4 px-8 rounded-full border"
      >
        {{ item[1] }}
      </p>
    </div>
    <div class="posts flex flex-col">
      <postPreview v-for="(item, index) in active" v-show="index < max" :key="item" :text="item"/>
    </div>
    <div class="footer flex flex-col w-full mb-60">
      <div class="flex flex-col">
        <div class="become-client ml-41.5p " v-if="left > 0" @click="expandMax()">
          <div class="connect-content flex justify-start items-center cursor-pointer w-max"  >
            <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
              <div
                class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
              ></div>
              <div
                class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
              ></div>
            </div>
            <p class="uppercase font-semibold fz-13" >{{ text.show[0] }}{{ add }}{{ text.show[1] }}{{left}}{{ text.show[2] }}</p>
          </div>

          <div class="connect-grad relative" style="z-index: -1">
            <div id="grad-1"></div>
            <div id="grad-2"></div>
            <div id="grad-3"></div>
          </div>
        </div>
        <p class="uppercase font-semibold fz-13 mx-auto" v-if="active.length === 0" >{{text.noPosts}}</p>
      </div>
      <div class="flex justify-between mt-37">
        <p class="fz-10 font-medium" style="letter-spacing: 2px; color: rgba(110, 117, 141, 1)">
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
  props:['lang'],
  data(){
    return{
      activeTopic:"all",
      addDefault: 5,
      max:5
    }
  },
  components:{
    postPreview
  },
  methods:{
    expandMax(){
      let result = this.addDefault
      if (this.max + this.addDefault > this.active.length){
        result = this.active.length - this.max
      }
      this.max+=result
    },
    setTopic(item){
      this.activeTopic = item
      this.max = this.addDefault
    }
  },
  computed:{
    add(){
      let result = this.addDefault
      if (this.max + this.addDefault > this.active.length){
        result = this.active.length - this.max
      }
      return result
    },
    left(){
      return this.active.length - this.max
    },
    text(){
      return require("@/assets/text/blog/page/ru.json")
    },
    active(){
      return this.text.previews.filter(item=>item.tagCodes.includes(this.activeTopic) || this.activeTopic === 'all')
    }
  },
  mounted() {
    console.log(this.active.length);
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
