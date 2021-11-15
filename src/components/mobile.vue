<template>
  <div class="overflow-hidden relative top-50vh">
    <Main/>
  </div>

</template>

<script>
import Main from "@/components/mobile/pages/main.vue";

export default {
  name: "mobile",
  props:['lang'],
  components: {
    Main,
  },
};
</script>

<style scoped></style>
