<template>
  <div
    id="slide-1"
    @scroll.stop=""
    class="slide ml-83 pt-23.5 h-screen relative"
  >
    <servicesScreen />
    <firstAnimation />
    <div class="news flex mt-18.75 ml-66 cursor-pointer w-max">
      <div>
        <p
          class="font-medium uppercase text-xxs"
          style="letter-spacing: 0.3em; color: #ff2e53"
        >
          HOT NEWS
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
        <p class="font-medium text-xsm relative -top-2">
          Max Frai Agency & Atlas <br />
          Weekend: технические решения <br />
          для масшатбных проектов в <br />
          условиях пандемии
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
