<template>
  <mobile :lang="'ru'" class="xl:hidden"/>

</template>

<script>
import mobile from "./components/mobile.vue"

import './assets/fonts.css'

export default {
  name: "App",
  components:{
    mobile
  }
};
</script>

<style lang="scss">

</style>
