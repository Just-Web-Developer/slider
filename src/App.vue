<template>
  <FixWrapper />
  <div id="slide-1" class="slide ml-83 pt-23.5 h-screen relative">
    <servicesScreen />
    <video
      autoplay
      loop
      muted
      class="absolute w-240 right-0 top-0"
      style="z-index: -10"
      src="./assets/videos/1_slide.mp4"
    ></video>
  </div>
</template>

<script>
import FixWrapper from "@/components/FixWrapper";
import servicesScreen from "@/components/servicesScreen";

export default {
  name: "App",
  components: {
    FixWrapper,
    servicesScreen,
  },
};
</script>

<style lang="scss" scoped></style>
