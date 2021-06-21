<template>
  <div id="slide-6" class="slide ml-83 pt-52 h-screen relative flex h-125">
    <div class="blog-left w-68">
      <img src="../assets/images/volume.svg" class="w-10 h-10 mt-17"  alt="">
    </div>
    <div class="blog-right flex flex-col">
      <p
        class=" uppercase text-xxs font-medium mb-15"
        style="color: rgba(110, 117, 141, 1); letter-spacing: 2px">
        blog
      </p>
      <div class="blog-container flex w-250 justify-between">
        <div class="new w-55" v-for="item in news" :key="item">
          <p class="font-medium text-base mb-6 h-38" style="color:rgba(110, 117, 141, 1);">
            {{item.text}}
          </p>
          <div class="overflow-hidden w-42.5 h-42.5">
            <img :src="require('../assets/images/slide_6/'+ item.image + '.png')" class="w-42.5 h-42.5 " :style="'transform-origin:'+item.pos+';transform: scale('+item.scale+');'" alt="">
          </div>

        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "slide6",
  data(){
    return{
      news:[
        {
          scale: "1.3,1",
          pos: 'center',
          image:"max",
          text:"Макс Фрай в интервью ресурсу AIN.UA: об агентстве, направлениях работы и планах на будущее"
        },
        {
          scale: "1.3,1",
          pos: 'center',
          image:"atlas",
          text:"Atlas Weekend: комплексное решение больших проблем. Как писалась и совершенствовалась система"
        },
        {
          scale: "1.7,1.3",
          pos: 'right',
          image:"sluhay",
          text:"Слухай – библиотека аудиокниг программы ВНО. От идеи до реализации, – Макс Фрай"
        },
        {
          scale: "1.3,1",
          pos: 'center',
          image:"bitcoin",
          text:"Макс Фрай запустил криптовалютную биржу – зачем, кому и как"
        }
      ]
    }
  }
};
</script>

<style lang="scss" scoped>

</style>
