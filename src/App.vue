<template>
  <FixWrapper />
  <div id="slide-1" class="slide ml-83 pt-23.5 h-screen">
    <div class=" mt-44 relative w-200 h-67.5 services" :class="servicesClass">
      <div id="first-service" @mouseover="servicesClass='first-state'" @mouseleave="servicesClass='null-state'" class="absolute">
        <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
          <transition name="service-count">
            <span v-if="servicesClass !== 'first-state'" class="absolute top-0 left-0">01</span>
          </transition>
          <p class="font-medium text-white uppercase ml-0" :class="servicesClass === 'first-state' ? 'ml-100p transform -translate-x-full' : ''">создаём</p>
          <transition name="service-hover-screen">
            <div v-if="servicesClass === 'first-state'" class=" absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5">
              <div class="flex justify-between">
                <img  v-if="servicesClass === 'first-state'" src="../src/assets/images/service_icons/loader.svg" class="icon" alt="">
                <p class="font-medium text-white uppercase">создаём</p>
              </div>
              <div class="flex flex-col mt-auto ml-auto items-end">
                <p><img src="src/assets/images/service_icons/cross.svg" class="w-full ml-4" alt=""></p>
                <p><img src="src/assets/images/service_icons/cross.svg" class="w-full ml-4" alt=""></p>
                <p><img src="src/assets/images/service_icons/cross.svg" class="w-full ml-4" alt=""></p>
              </div>
            </div>
          </transition>

        </div>
      </div>
      <div id="second-service" @mouseover="servicesClass='second-state'" @mouseout="servicesClass='null-state'" class="absolute">
        <div class="relative pt-7.5 pr-7.5 overflow-hidden label">
          <transition name="service-count">
            <span v-if="servicesClass !== 'second-state'" class="absolute top-0 left-0">02</span>
          </transition>
          <p class="font-medium text-white uppercase">ведём</p>
        </div>
      </div>
      <div id="third-service" @mouseover="servicesClass='third-state'" @mouseout="servicesClass='null-state'" class="absolute">
        <div class="relative pt-7.5 pr-7.5 overflow-hidden label">
          <transition name="service-count">
            <span v-if="servicesClass !== 'third-state'" class="absolute top-0 left-0">03</span>
          </transition>
          <p class="font-medium text-white uppercase">продвигаем</p>
        </div>
      </div>
      <div id="fourth-service" @mouseover="servicesClass='fourth-state'" @mouseout="servicesClass='null-state'" class="absolute">
        <div class="relative pt-7.5 pr-7.5 overflow-hidden label">
          <transition name="service-count">
            <span v-if="servicesClass !== 'fourth-state'" class="absolute top-0 left-0">04</span>
          </transition>
          <p class="font-medium text-white uppercase">пишем</p>
        </div>
      </div>
      <div id="fifth-service" @mouseover="servicesClass='fifth-state'" @mouseout="servicesClass='null-state'" class="absolute">
        <div class="relative pt-7.5 pr-7.5 overflow-hidden label">
          <transition name="service-count">
            <span v-if="servicesClass !== 'fifth-state'" class="absolute top-0 left-0">05</span>
          </transition>
          <p class="font-medium text-white uppercase">помогаем</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FixWrapper from "@/components/FixWrapper";

export default {
  name: "App",
  components: {
    FixWrapper,
  },
  data(){
    return{
      servicesClass: 'first-state'
    }
  }
};
</script>

<style lang="scss" scoped>
.services{
  &>div{
    transition: all .3s linear;
    .label {
      p{
        font-size: 1.25rem;
        line-height: 2.5rem;
        transition: all .3s linear;
      }
      span{
        color:rgba(151, 163, 203, 0.6);
        font-size: 0.625rem;
        line-height: 0.625rem;
      }
    }
    .hover-screen{
      background: rgba(23, 26, 31, 1);
      z-index: -1;
    }
  }
  //#first-service{
  //  background: red;
  //}
  //#second-service{
  //  background: blue;
  //}
  //#third-service{
  //  background: green;
  //}
  //#fourth-service{
  //  background: yellow;
  //}
  //#fifth-service{
  //  background: orange;
  //}
}
.services.null-state{
  &>div{
    width: 33.3%;
    height: 50%;
  }
  #first-service{
    top: 0;
    left: 0;
  }
  #second-service{
    top: 0;
    left: 33.3%;
  }
  #third-service{
    top: 0;
    left: 66.6%;
  }
  #fourth-service{
    top: 33.3%;
    left: 33.3%;
  }
  #fifth-service{
    top: 33.3%;
    left: 66.6%;
  }
}

.services.first-state{
  &>div{
    transition: all .3s linear;
  }
  #first-service{
    top: 0;
    left: 0;
    height: 100%;
    width: 40%;
  }
  #second-service{
    top: 0;
    left: 46.6%;
    height: 33.3%;
    width: 20%;
  }
  #third-service{
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service{
    top: 33.3%;
    left: 46.6%;
    height: 33.3%;
    width: 20%;
  }
  #fifth-service{
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #second-service .label>p, #third-service .label>p,#fourth-service .label>p, #fifth-service .label>p{
    font-size: 1rem;
    color:rgba(151, 163, 203, 0.6);
  }
}

.services.second-state{
  &>div{
    transition: all .3s linear;

  }
  #first-service{
    top: 0;
    left: 0;
    height: 33.3%;
    width: 20%;
  }
  #second-service{
    top: 0;
    left: 20%;
    height: 100%;
    width: 40%;

  }
  #third-service{
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service{
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fifth-service{
    top: 66.6%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #first-service .label>p, #third-service .label>p,#fourth-service .label>p, #fifth-service .label>p{
    font-size: 1rem;
    color:rgba(151, 163, 203, 0.6);
  }
}

.services.third-state{
  &>div{
    transition: all .3s linear;
  }
  #first-service{
    top: 0;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #second-service{
    top: 0;
    left: 25%;
    height: 33.3%;
    width: 25%;

  }
  #third-service{
    top: 0;
    left: 56.6%;
    height: 100%;
    width: 40%;
  }
  #fourth-service{
    top: 33.3%;
    left: 0%;
    height: 33.3%;
    width: 25%;
  }
  #fifth-service{
    top: 33.3%;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #second-service .label>p, #first-service .label>p,#fourth-service .label>p, #fifth-service .label>p{
    font-size: 1rem;
    color:rgba(151, 163, 203, 0.6);
  }
}

.services.fourth-state{
  &>div{
    transition: all .3s linear;
  }
  #first-service{
    top: 0;
    left: 0;
    height: 33.3%;
    width: 20%;
  }
  #second-service{
    top: 33.3%;
    left: 0%;
    height: 33.3%;
    width: 20%;
  }
  #third-service{
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service{
    top: 0%;
    left: 20%;
    height: 100%;
    width: 40%;
  }
  #fifth-service{
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #second-service .label>p, #third-service .label>p,#first-service .label>p, #fifth-service .label>p{
    font-size: 1rem;
    color:rgba(151, 163, 203, 0.6);
  }
}

.services.fifth-state{
  &>div{
    transition: all .3s linear;
  }
  #first-service{
    top: 0;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #second-service{
    top: 0;
    left: 25%;
    height: 33.3%;
    width: 25%;

  }
  #third-service{
    top: 33.3%;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #fourth-service{
    top: 33.3%;
    left: 0%;
    height: 33.3%;
    width: 25%;
  }
  #fifth-service{
    top: 0;
    left: 56.6%;
    height: 100%;
    width: 40%;
  }
  #second-service .label>p, #third-service .label>p,#fourth-service .label>p, #first-service .label>p{
    font-size: 1rem;
    color:rgba(151, 163, 203, 0.6);
  }
}


.service-count-enter-active,
.service-count-leave-active,
.service-hover-screen-enter-active,
.service-hover-screen-leave-active,{
  transition: all .3s linear;
  .icon{
    transition: all .3s linear;
  }
}

.service-count-enter-from,
.service-count-leave-to {
  transform: translateX(300%);
  opacity: 0;
}

.service-hover-screen-enter-from,
.service-hover-screen-leave-to {
  transform: translateX(-100%);
  opacity: 0;
  .icon{
    transform:translateY(-9%)  rotate(180deg) ;
  }
}





</style>
