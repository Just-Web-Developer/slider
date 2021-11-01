<template>
  <div class="flex post-preview mb-37.5 cursor-pointer">
    <div class="left flex w-112 flex-col">
      <p class="date font-medium fz-10 mb-12" style="color:rgba(110, 117, 141, 1); line-height: 2px;letter-spacing: 0.3rem">
        {{ text.date }}</p>
      <h3 class="title fz-24 pr-0.5" style="color: rgba(192, 197, 216, 1)">
        {{ text.title }}
      </h3>
      <div class="tags flex mt-45 ">
        <p class="posts-topic cursor-pointer font-semibold fz-13 uppercase py-2 px-4 rounded-full border " v-for="(item, index) in text.tags" :key="item" :class="{'mr-4': index !== text.tags.length-1}">
          {{ item }}
        </p>
      </div>
    </div>
    <div class="image w-152.5 h-105 ml-12 mr-11.25 overflow-hidden">
      <img :src="require('@/assets/images/blog/' + text.id + '.jpg')" class="w-152.5 h-105" alt="">
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
  name: "postPreview",
  props:['text']
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
