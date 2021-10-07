<template>
  <div class="fixed" style="z-index: 202;">
    <transition name="contact">
      <div v-if="!firstStep" class="absolute screen pt-12.5 pl-82.5 pr-17.25  h-screen w-screen" :style="'top: ' + (slide-1) + '00vh'">
        <contactFirst :text="text.first"  @closeContacts="$emit('closeContacts')" @nextStage="nextStep($event)"  />
      </div>
      <div v-else class="absolute screen pt-12.5 pl-82.5 pr-17.25 h-screen w-screen" :style="'top: ' + (slide-1) + '00vh'">
        <contactSecond :text="text.second" :choice="choice" @closeContacts="$emit('closeContacts')"/>
      </div>
    </transition>
  </div>


</template>

<script>
import contactFirst from "./contactFirst";
import contactSecond from "./contactSecond";

export default {
  name: "contact",
  emits:['closeContacts'],
  props:['slide'],
  components:{contactFirst, contactSecond},
  data(){
    return{
      firstStep:false,
      choice:''
    }
  },
  methods:{
    nextStep(e){
      this.choice = e
      this.firstStep = true
    }
  },
  computed:{
    text(){
      return require("@/assets/text/contact/ru.json")
    }
  }
};
</script>

<style lang="scss">
.screen{
  background: #323749;
  left: 0;
}

.contact-enter-active,
.contact-leave-active{
  transition: all .3s linear;
}
.contact-enter-from{
  left: 100vw;
}
.contact-leave-to{
  left: -100vw;
}

</style>
