<template>
  <div class="body" @scroll="$event.preventDefault()" :class="'slide-'+slide">
    <FixWrapper @nextSlide="nextSlide()" @prevSlide="prevSlide()" :state="slide" />
    <div id="slide-1" class="slide ml-83 pt-23.5 h-screen relative">
      <servicesScreen />
      <firstAnimation/>
      <div class="news flex mt-18.75 ml-66 cursor-pointer w-max">
        <div>
          <p class="font-medium uppercase text-xxs" style="letter-spacing: 0.3em;color: #FF2E53;">HOT NEWS</p>
          <svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 17L19 10L12 3" stroke-width="2" stroke-linejoin="round"/>
            <path d="M5 10L19 10" stroke-width="2" stroke-linejoin="round"/>
          </svg>
        </div>
        <div class="ml-47 right">
          <p class="font-medium text-xsm relative -top-2">
            Max Frai Agency & Atlas <br> Weekend: технические решения <br> для масшатбных проектов в <br> условиях пандемии
          </p>
        </div>

      </div>
    </div>
    <div class="gradient">
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: -518px;top: 107px;background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 133, 255, 0) 100%);"></div>
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: -322px;top: 391px;background: radial-gradient(50% 50% at 50% 50%, rgba(242, 41, 89, 0.3) 0%, rgba(242, 41, 89, 0) 100%);"></div>
      <div style="z-index: -10;position: absolute;width: 1122px;height: 1122px;left: 101px;top: 779px;background: radial-gradient(50% 50% at 50% 50%, rgba(0, 133, 255, 0.2) 0%, rgba(0, 128, 247, 0) 100%);"></div>
    </div>
    <div id="slide-2" class="slide ml-83 pt-23.5 h-screen relative">

    </div>
  </div>

</template>

<script>
import FixWrapper from "@/components/FixWrapper";
import servicesScreen from "@/components/servicesScreen";
import firstAnimation from "@/components/firstAnimation";

export default {
  name: "App",
  components: {
    FixWrapper,
    servicesScreen,
    firstAnimation
  },
  data(){
    return{
      slide: 1,
      max:7
    }
  },
  methods:{
    nextSlide(){
      if (this.slide <= this.max){
        this.slide++
      }
      else{
        this.slide = 1
      }
    },
    prevSlide(){
      if (this.slide !== 1){
        this.slide--
      }
    }
  }
};
</script>

<style lang="scss" scoped>
.body{
  font-family: 'Montserrat', sans-serif;
  color: white;
  height: 700vh;
  position: relative;
  transition: all linear 1s;
  top: 0;
}
.body.slide-1{
  top: 0;
}
.body.slide-2{
  top:-100vh;
}
.body.slide-3{
  top:-200vh;
}
.body.slide-4{
  top:-300vh;
}
.body.slide-5{
  top:-400vh;
}
.body.slide-6{
  top:-500vh;
}
.body.slide-7{
  top:-600vh;
}
.news{
  .right{
    p{
      transition: all linear .3s;
      color: #C0C5D8;
    }
  }
  svg{
    margin-left: 0;
    margin-top: 2rem;
    transition: all linear .3s;
    path{
      transition: all linear .3s;

      stroke: white;
    }
  }
}
.news:hover{
  svg{
    margin-left: 3.5rem;
    transition: all linear .3s;
    path{
      transition: all linear .3s;

      stroke: #FF2E53;
    }
  }
  .right{
    p{
      transition: all linear .3s;
      color: white;
    }
  }
}
</style>
