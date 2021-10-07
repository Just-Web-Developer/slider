<template>
  <projectWrapper @projects="$emit('projects')" @nav="$emit('nav')"/>
  <div id="project" class="pt-50 pl-82.5 pr-50 w-full flex flex-col slide min-h-screen">
    <div class="header pr-32.5 flex">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-4.5xl" style="color: #FF2E53">Atlas Weekend</h2>
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
              <p class="uppercase font-medium text-xs mb-5" style="color:#6E758D;">ЗАДАЧА:</p>
              <p class="text-base font-medium w-87.5">создать систему управления всем фестивалем</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
          <div class="top-right flex flex-col w-55">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content mt-5 mb-10">
              <p class="uppercase font-medium text-xs mb-5 w-38" style="color:#6E758D;">СРОКИ РЕАЛИЗАЦИИ, МЕСЯЦЕВ</p>
              <p class="text-5.5xl">1,5</p>
            </div>
            <div class="line w-full mt-auto h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
        </div>
        <p class="mt-37.5 text-xxl font-medium">Atlas Weekend – один из масштабнейших музыкальных фестивалей Украины и Европы. В 2019 году его посетило более 530 тыс людей и мы гордимся тем, что смогли сделать их отдых комфортней</p>
      </div>

    </div>
    <img src="@/assets/images/projects/01/first.png" alt="" class="first-image pr-32.5 mt-50">

    <p class="prolog pr-32.5 mt-50 ml-130.7 font-medium text-xxl">Впервые за проект Макс Фрай взялся в 2017 году, когда было принято решение отказаться от предыдущего билетного оператора.</p>

    <div class="problems pr-32.5 flex mt-37.5">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-3.55xl w-87.5" style="color: #FF2E53">Проблемы, которые стояли перед организаторами:</h2>

      </div>
      <div class="right flex flex-col">
        <div class="top flex">
          <div class="top-left flex flex-col w-87.5 mr-10">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">01</h6>
              <p class="text-base font-medium w-80">не было четкой системы мониторинга фестиваля</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">03</h6>
              <p class="text-base font-medium w-80">отсутствие системы оплаты на фудкортах</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
          <div class="top-right flex flex-col w-87.5">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">02</h6>
              <p class="text-base font-medium w-80 h-12">огромные очереди на вход</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs mb-5" style="color:#6E758D;letter-spacing: 0.3rem">04</h6>
              <p class="text-base font-medium w-80">нелегальная продажа/перепродажа билетов и прочее</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>
        </div>
      </div>

    </div>

    <doubleSlider :text="text" :src="'projects'" class="mt-65 mb-50"/>

    <div class="result pr-32.5 flex mt-37.5">
      <div class="left flex flex-col w-130.7 flex-shrink-0 justify-between items-start">
        <h2 class="font-light text-3.55xl w-87.5" style="color: #FF2E53">Результат: </h2>

      </div>
      <div class="right flex flex-col">
        <div class="top flex">
          <div class="top-left flex flex-col w-87.5 mr-10">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">01</h6>
              <p class="text-base font-medium w-80 h-18.75">удалось минимизировать очереди на входе, а соответственно негатив в адрес организаторов</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">03</h6>
              <p class="text-base font-medium w-80 h-25">сделать удобную систему мониторинга, которая отображает состояние фестиваля в реальном времени</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">05</h6>
              <p class="text-base font-medium w-80 h-25">эффективно бороться с перекупами/перепродажей браслетов, то есть сохранить фестивалю более 2 млн грн</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
          </div>


          <div class="top-right flex flex-col w-87.5">
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">02</h6>
              <p class="text-base font-medium w-80 h-18.75">создать свою систему оплаты на фудкортах</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">04</h6>
              <p class="text-base font-medium w-80 h-25">автоматизировать и упростить работу с персоналом</p>
            </div>
            <div class="line w-full h-px" style="background:rgba(151, 163, 203, 0.3);"></div>
            <div class="content my-7.5">
              <h6 class="mb-7.5 uppercase font-medium text-xs" style="color:#6E758D;letter-spacing: 0.3rem">06</h6>
              <p class="text-base font-medium w-80 h-25">создать гибкий контроль доступа к сценам, фестивалю, въезду автомобилей в разные даты и время</p>
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
    <div class="next w-315 cursor-pointer relative">
      <!-- Background start -->
      <div class="absolute w-full h-full shadow z-10"></div>
      <img class="w-full" src="@/assets/images/projects/01/next.png" alt="">
      <div class="line absolute bottom-0 h-2"></div>
      <!-- Background end -->
      <div class="content absolute z-20 bottom-23 left-10">
        <p class="next-post-title text-xxsm uppercase font-semibold mb-6">СЛЕДУЮЩАЯ статья</p>
        <h3 class="w-110 text-3.55xl">Graphic Design Trends 2021 Inspired By What We All Experienced This Year</h3>
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
  data(){
    return{
      text:{
        images: ['01','02','03','04']
      }
    }
  },
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