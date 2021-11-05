<template>
  <div >
    <firstAnimation class="relative h-125 w-screen overflow-hidden" :mobile="true"/>
  </div>

</template>

<script>
import firstAnimation from "../../desktop/slide1/firstAnimation";

export default {
  name: "slide1",
  components:{firstAnimation}
};
</script>

<style>
</style>