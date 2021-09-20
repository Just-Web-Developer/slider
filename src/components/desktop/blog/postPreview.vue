<template>
  <div class="flex post-preview mb-37.5 cursor-pointer">
    <div class="left flex w-112 flex-col">
      <p class="date font-medium text-xxs mb-12" style="color:rgba(110, 117, 141, 1); line-height: 2px;letter-spacing: 0.3rem">01.04.2021</p>
      <h3 class="title text-2xl pr-0.5" style="color: rgba(192, 197, 216, 1)">
        Макс Фрай в интервью ресурсу AIN.UA: об агентстве, направлениях работы и планах на будущее
      </h3>
      <div class="tags flex mt-45 ">
        <p class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-2 px-4 rounded-full border mr-4">
          новости
        </p>
        <p class="posts-topic cursor-pointer font-semibold text-xxsm uppercase py-2 px-4 rounded-full border">
          РАЗНОЕ
        </p>
      </div>
    </div>
    <div class="image w-152.5 h-105 ml-12 mr-11.25 overflow-hidden">
      <img src="@/assets/images/blog/01.jpg" class="w-152.5 h-105" alt="">
    </div>
    <div class="arrow">
      <svg width="21" height="19.5" viewBox="0 0 21 19.5" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1.5 9L10.5 18L19.5 9" stroke="white" stroke-linejoin="round"/>
        <path d="M10.49997 0V18" stroke="white" stroke-linejoin="round"/>
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  name: "postPreview"
};
</script>

<style lang="scss" scoped>
.image img, svg{
  transition: all linear .3s;

}
svg{
  transform: rotate(-90deg);
  path{
    stroke: #323749;
    transition: all linear .3s;
  }
}
.post-preview:hover{

  .image img{
    transform: scale(1.2);
  }
  svg{
    path{
      stroke: white;
    }
    transform: rotate(-90deg) translateY(453%);
  }

}
</style>
