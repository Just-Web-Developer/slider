<template>
  <div class="fixed z-80">
    <transition name="contact">
      <div v-if="!firstStep" class="absolute screen pt-12.5 pl-82.5 pr-17.25  h-screen w-screen">
        <contactFirst  @closeContacts="$emit('closeContacts')" @nextStage="nextStep($event)"  />
      </div>
      <div v-else class="absolute screen pt-12.5 pl-82.5 pr-17.25 h-screen w-screen">
        <contactSecond :choice="choice" @closeContacts="$emit('closeContacts')"/>
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
