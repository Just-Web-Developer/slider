<template>
  <div>
    <Navbar :lang="lang" />
    <Main />
  </div>

</template>

<script>
import Main from "@/components/mobile/pages/main.vue";
import Navbar from "./mobile/reuseable/navbar";

export default {
  name: "mobile",
  props:['lang'],
  components: {
    Main,
    Navbar
  },
};
</script>

<style scoped></style>
