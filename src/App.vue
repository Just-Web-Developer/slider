<template>
  <mobile :lang="'ru'" class="xl:hidden"/>
  <desktop class="hidden xl:block"/>

</template>

<script>
import mobile from "./components/mobile.vue"
import desktop from "./components/desktop";

import './assets/fonts.css'

export default {
  name: "App",
  components:{
    desktop,
    mobile
  }
};
</script>

<style lang="scss">

</style>
