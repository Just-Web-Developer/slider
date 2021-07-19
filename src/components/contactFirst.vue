<template>
  <div class="flex header">
    <div class="max-frai">
      <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
      <p
        class="uppercase inter font-bold mt-4 text-xxs"
        style="color: #ff2e53; letter-spacing: 1rem;"
      >
        AGENCY
      </p>
    </div>
    <div class="ml-27 h-full mt-auto">
      <div class="h-8px w-px" style="background: #ff2e53"></div>
    </div>
    <div class="ml-65 agency">
      <p class="font-medium text-base" @mouseover="agencyGradsOn" @mouseleave="agencyGradsOff">
        Агентство простых решений сложного <br />
        цифрового мира
      </p>
    </div>
    <div class="close ml-auto flex flex-col items-center cursor-pointer" @click="$emit('closeContacts')">
      <p class="text-xxs uppercase" style="letter-spacing: 0.3rem">close</p>
      <div class="close w-5 h-5 relative mt-4" >
        <div class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-45" style="background:white;"></div>
        <div class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 -rotate-45" style="background:white;"></div>
      </div>
    </div>
  </div>
  <div class="mt-22.5">
    <h4 class="uppercase text-xxl font-medium">Решение в пару кликов</h4>
    <p class="mt-6 text-lg" style="color:rgba(110, 117, 141, 1);">Что тебя интересует?</p>
    <div class="services mt-15 w-max grid gap-10 grid-cols-3 grid-rows-2">

      <div @click="$emit('nextStage', 'разработка')" class="service cursor-pointer overflow-hidden relative p-7.5 w-87.5 h-50 flex flex-col justify-between box-border" style="border: 1px solid rgba(110, 117, 141, 0.2);">
        <p class="text-base relative z-10">Разработка</p>
        <svg class="w-12 h-12 relative z-10" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25 4.16667V12.5" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M25 37.5V45.8333" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.2708 10.2708L16.1667 16.1667" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M33.8333 33.8333L39.7292 39.7292" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M4.16666 25H12.5" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M37.5 25H45.8333" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.2708 39.7292L16.1667 33.8333" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M33.8333 16.1667L39.7292 10.2708" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div class="connect-grad absolute" style="z-index: 1">
          <div class="grad-1"></div>
          <div class="grad-2"></div>
          <div class="grad-3"></div>
        </div>
      </div>

      <div @click="$emit('nextStage', 'поддержка')" class="service cursor-pointer overflow-hidden relative p-7.5 w-87.5 h-50 flex flex-col justify-between box-border" style="border: 1px solid rgba(110, 117, 141, 0.2);">
        <p class="text-base relative z-10">Техническая поддержка</p>
        <svg class="w-12 h-12 relative z-10" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25 45.8333C36.5059 45.8333 45.8333 36.5059 45.8333 25C45.8333 13.4941 36.5059 4.16667 25 4.16667C13.4941 4.16667 4.16667 13.4941 4.16667 25C4.16667 36.5059 13.4941 45.8333 25 45.8333Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M25 33.3333C29.6024 33.3333 33.3333 29.6024 33.3333 25C33.3333 20.3976 29.6024 16.6667 25 16.6667C20.3976 16.6667 16.6667 20.3976 16.6667 25C16.6667 29.6024 20.3976 33.3333 25 33.3333Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.2708 10.2708L19.1042 19.1042" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M30.8958 30.8958L39.7292 39.7292" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M30.8958 19.1042L39.7292 10.2708" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M30.8958 19.1042L38.25 11.75" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M10.2708 39.7292L19.1042 30.8958" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div class="connect-grad absolute" style="z-index: 1">
          <div class="grad-1"></div>
          <div class="grad-2"></div>
          <div class="grad-3"></div>
        </div>
      </div>

      <div @click="$emit('nextStage', 'решения')" class="service cursor-pointer overflow-hidden relative p-7.5 w-87.5 h-50 flex flex-col justify-between box-border" style="border: 1px solid rgba(110, 117, 141, 0.2);">
        <p class="text-base relative z-10">Готовые технические <br> решения</p>
        <svg class="w-12 h-12 relative z-10" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M20.8333 6.25H6.25V20.8333H20.8333V6.25Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M43.75 6.25H29.1667V20.8333H43.75V6.25Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M43.75 29.1667H29.1667V43.75H43.75V29.1667Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M20.8333 29.1667H6.25V43.75H20.8333V29.1667Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div class="connect-grad absolute" style="z-index: 1">
          <div class="grad-1"></div>
          <div class="grad-2"></div>
          <div class="grad-3"></div>
        </div>
      </div>

      <div @click="$emit('nextStage', 'креатив')" class="service cursor-pointer overflow-hidden relative p-7.5 w-87.5 h-50 flex flex-col justify-between box-border" style="border: 1px solid rgba(110, 117, 141, 0.2);">
        <p class="text-base relative z-10">Креатив</p>
        <svg class="w-12.5 h-12.5 relative z-10" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M37.5 6.25C35.8424 6.25 34.2527 6.90848 33.0806 8.08058C31.9085 9.25269 31.25 10.8424 31.25 12.5V37.5C31.25 39.1576 31.9085 40.7473 33.0806 41.9194C34.2527 43.0915 35.8424 43.75 37.5 43.75C39.1576 43.75 40.7473 43.0915 41.9194 41.9194C43.0915 40.7473 43.75 39.1576 43.75 37.5C43.75 35.8424 43.0915 34.2527 41.9194 33.0806C40.7473 31.9085 39.1576 31.25 37.5 31.25H12.5C10.8424 31.25 9.25269 31.9085 8.08058 33.0806C6.90848 34.2527 6.25 35.8424 6.25 37.5C6.25 39.1576 6.90848 40.7473 8.08058 41.9194C9.25269 43.0915 10.8424 43.75 12.5 43.75C14.1576 43.75 15.7473 43.0915 16.9194 41.9194C18.0915 40.7473 18.75 39.1576 18.75 37.5V12.5C18.75 10.8424 18.0915 9.25269 16.9194 8.08058C15.7473 6.90848 14.1576 6.25 12.5 6.25C10.8424 6.25 9.25269 6.90848 8.08058 8.08058C6.90848 9.25269 6.25 10.8424 6.25 12.5C6.25 14.1576 6.90848 15.7473 8.08058 16.9194C9.25269 18.0915 10.8424 18.75 12.5 18.75H37.5C39.1576 18.75 40.7473 18.0915 41.9194 16.9194C43.0915 15.7473 43.75 14.1576 43.75 12.5C43.75 10.8424 43.0915 9.25269 41.9194 8.08058C40.7473 6.90848 39.1576 6.25 37.5 6.25Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div class="connect-grad absolute" style="z-index: 1">
          <div class="grad-1"></div>
          <div class="grad-2"></div>
          <div class="grad-3"></div>
        </div>
      </div>

      <div @click="$emit('nextStage', 'стратегия')" class="service cursor-pointer overflow-hidden relative p-7.5 w-87.5 h-50 flex flex-col justify-between box-border" style="border: 1px solid rgba(110, 117, 141, 0.2);">
        <p class="text-base relative z-10">Стратегия</p>
        <svg class="w-12 h-12 relative z-10" viewBox="0 0 50 50" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M25 45.8333C36.5059 45.8333 45.8333 36.5059 45.8333 25C45.8333 13.4941 36.5059 4.16667 25 4.16667C13.4941 4.16667 4.16666 13.4941 4.16666 25C4.16666 36.5059 13.4941 45.8333 25 45.8333Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M33.8333 16.1667L29.4167 29.4167L16.1667 33.8333L20.5833 20.5833L33.8333 16.1667Z" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
        <div class="connect-grad absolute" style="z-index: 1">
          <div class="grad-1"></div>
          <div class="grad-2"></div>
          <div class="grad-3"></div>
        </div>
      </div>

      <div @click="$emit('nextStage', 'другое')" class="flex items-end justify-end ">
        <p class="font-semibold uppercase another cursor-pointer">Другое</p>
      </div>

    </div>
  </div>
</template>

<script>
export default {
  name: "contactFirst",
  emits:['closeContacts', 'nextStage']
};
</script>

<style lang="scss" scoped>
.service{
  background: transparent;
  &,*{
    transition: all ease-out .3s;
  }
  svg{
    path{
      stroke:#FF2E53;
    }
  }
  .connect-grad {
    left: -8rem;
    bottom: -1rem;
    div {
      border-radius: 50%;
      transform: scale(0);
      transition: all 0.3s ease-out;
    }
    .grad-1 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 66px;
      top: -120px;

      background: linear-gradient(
          321.88deg,
          rgba(7, 25, 61, 0) 12.53%,
          #f22959 43.45%,
          #ff0000 60.5%
      );
      filter: blur(30px);
      z-index: 2;
    }
    .grad-2 {
      position: absolute;
      width: 112.05px;
      height: 112.05px;
      left: 203.59px;
      top: -86.41px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(209.3deg, #7b61ff -2.55%, #7b61ff 64.59%);
      filter: blur(30px);
      z-index: 1;
    }
    .grad-3 {
      position: absolute;
      width: 180.46px;
      height: 180.46px;
      left: 136.28px;
      top: -21.72px;
      transform: rotate(165deg) scale(0);
      background: linear-gradient(
          209.3deg,
          rgba(242, 137, 41, 0) -2.55%,
          #f22959 64.59%
      );
      opacity: 0.7;
      filter: blur(30px);
      z-index: 1;
    }
  }
}
.service:hover{
  background: #000;
  p{
    font-size: 1.125rem;
    line-height: 1.75rem;
  }
  svg{
    transform: rotate(-180deg);
    path{
      stroke:white;
    }
  }
  .connect-grad {
    div {
      transform: scale(1);
    }
    .grad-2 {
      transform: rotate(165deg) scale(1);
    }
    .grad-3 {
      transform: rotate(165deg) scale(1);
    }
  }
}
.another{
  transition: all ease-out .3s;
  color:rgba(110, 117, 141, 1);
}
.another:hover{
  color: white;
}
</style>
