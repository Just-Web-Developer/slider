<template>
  <div
    id="slide-1"
    @scroll.stop=""
    class="slide ml-83 pt-23.5 h-screen relative"
  >
    <servicesScreen :text="text.services" />
    <firstAnimation />
    <div class="news flex mt-18.75 ml-66 cursor-pointer w-max">
      <div>
        <p
          class="font-medium uppercase fz-10"
          style="letter-spacing: 0.3em; color: #ff2e53"
        >
          {{text.news.hot}}
        </p>
        <svg
          width="20"
          height="20"
          viewBox="0 0 20 20"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M12 17L19 10L12 3"
            stroke-width="2"
            stroke-linejoin="round"
          />
          <path d="M5 10L19 10" stroke-width="2" stroke-linejoin="round" />
        </svg>
      </div>
      <div class="ml-47 right">
        <p class="font-medium fz-15 relative -top-2">
          {{text.news.text[0]}} <br />
          {{text.news.text[1]}} <br />
          {{text.news.text[2]}} <br />
          {{text.news.text[3]}}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import servicesScreen from "@/components/desktop/slide1/servicesScreen";
import firstAnimation from "@/components/desktop/slide1/firstAnimation";

export default {
  name: "slide1",
  components: { servicesScreen, firstAnimation },
  computed:{
    text(){
      return require("@/assets/text/main/slide1/ru.json")
    }
  },
  props:['lang']
};
</script>

<style lang="scss" scoped>
.news {
  .right {
    p {
      transition: all linear 0.3s;
      color: #c0c5d8;
    }
  }
  svg {
    margin-left: 0;
    margin-top: 2rem;
    transition: all linear 0.3s;
    path {
      transition: all linear 0.3s;

      stroke: white;
    }
  }
}
.news:hover {
  svg {
    margin-left: 3.5rem;
    transition: all linear 0.3s;
    path {
      transition: all linear 0.3s;

      stroke: #ff2e53;
    }
  }
  .right {
    p {
      transition: all linear 0.3s;
      color: white;
    }
  }
}
</style>
