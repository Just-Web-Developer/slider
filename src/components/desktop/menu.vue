<template>
  <div class="fixed top-0 left-0" style="z-index: 200;" >
      <div  class=" screen pt-55  h-screen w-screen fixed" :style="'top:0'">
        <div class="langs pl-82.5 flex">
          <div class="lang cursor-pointer mr-20" :class="{'active': language === 'ru'}" @click="chooseLang('ru')">
            <p class="uppercase text-xxsm font-semibold">русский</p>
            <div class="decorator mt-4.5 h-2px"></div>
          </div>
          <div class="lang cursor-pointer mr-20" :class="{'active': language === 'ua'}" @click="chooseLang('ua')">
            <p class="uppercase text-xxsm font-semibold">українська</p>
            <div class="decorator mt-4.5 h-2px"></div>
          </div>
          <div class="lang cursor-pointer" :class="{'active': language === 'en'}" @click="chooseLang('en')">
            <p class="uppercase text-xxsm font-semibold">english</p>
            <div class="decorator mt-4.5 h-2px"></div>
          </div>
        </div>
        <nav class="mt-12.5">
          <div  class="nav-item flex items-center relative pl-82.5 pt-7.5 pb-8.75 bg-red-600">
            <div class="nav-background absolute top-0 right-0 bottom-0 left-0"></div>
            <h3 @click="chooseNav('agency')" class="relative z-10 font-medium text-xl uppercase cursor-pointer">{{ text.agency }}</h3>
            <div class="plus w-5 h-5 relative ml-90">
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-90"></div>
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2"></div>
            </div>
          </div>
          <div  class="nav-item flex items-center relative pl-82.5 pt-7.5 pb-8.75 bg-red-600">
            <div class="nav-background absolute top-0 right-0 bottom-0 left-0"></div>
            <h3 @click="chooseNav('projects')" class="relative z-10 font-medium text-xl uppercase cursor-pointer">{{ text.projects }}</h3>
            <div class="plus w-5 h-5 relative ml-90">
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-90"></div>
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2"></div>
            </div>
          </div>
          <div  class="nav-item flex items-center relative pl-82.5 pt-7.5 pb-8.75 bg-red-600">
            <div class="nav-background absolute top-0 right-0 bottom-0 left-0"></div>
            <h3 @click="chooseNav('blog')" class="relative z-10 font-medium text-xl uppercase cursor-pointer">{{ text.blog }}</h3>
            <div class="plus w-5 h-5 relative ml-90">
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-90"></div>
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2"></div>
            </div>
          </div>
          <div  class="nav-item flex items-center relative pl-82.5 pt-7.5 pb-8.75 bg-red-600">
            <div class="nav-background absolute top-0 right-0 bottom-0 left-0"></div>
            <h3 @click="chooseNav('contacts')" class="relative z-10 font-medium text-xl uppercase cursor-pointer">{{ text.contacts }}</h3>
            <div class="plus w-5 h-5 relative ml-90">
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-90"></div>
              <div class="absolute w-4 h-2px bg-white left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2"></div>
            </div>
          </div>
        </nav>
      </div>
  </div>
</template>

<script>
export default {
  name: "Menu",
  props:['slide', 'language', 'content'],
  emits:['setNavRoute', 'setLang'],
  methods:{
    chooseNav(choice){
      this.$emit('setNavRoute', choice)
    },
    chooseLang(lang){
      this.$emit('setLang', lang)
    }
  },
  computed:{
    absolute(){
      return this.content !== 'post' && this.content !== 'project' && this.content !== 'blog'
    },
    text(){
      return require("@/assets/text/menu/ru.json")
    }
  }
};
</script>

<style scoped lang="scss">
.screen{
  background: #323749;
  left: 0;
  position: absolute;
}

.menu-enter-active,
.menu-leave-active{
  transition: all .3s linear;

}
.menu-enter-from,
.menu-leave-to{
  left: -100vw;
}
.lang{
  p{
    color: rgba(110, 117, 141, 1);
    transition: all linear .2s;
  }
  .decorator{
    transition: all linear .2s;
    width: 0%;
    background: rgba(255, 46, 83, 1);
  }
}
.lang:hover, .lang.active{
  p{
    color: white;
  }
  .decorator{
    width: 100%;
  }
}
.nav-item{
  .plus{
    transform: translateX(-300%) rotate(360deg);
    opacity: 0;
    transition: all linear .3s;
  }
  background: transparent;
  .nav-background{
    z-index: 0;
    opacity: 0;
    background: radial-gradient(88.44% 32601.6% at 100% 0%, rgba(50, 55, 73, 0) 5.3%, rgba(0, 133, 255, 0.15) 48.49%, #ff2e53 100%);
    transition: all linear .3s;
  }

  h3{
    transition: all linear .3s;
    color: rgba(110, 117, 141, 1);
  }
}
.nav-item:hover{
  .plus{
    transform: translateX(0) rotate(0);
    opacity: 1;
    transition: all linear .3s;
  }
  .nav-background{
    opacity: 1;
  }
  h3{
    color: white;
  }
}
</style>
