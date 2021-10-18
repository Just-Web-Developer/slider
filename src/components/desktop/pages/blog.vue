<template>
  <div class="blog relative overflow-scroll" id="blog" @wheel.stop>
    <blogWrappers :lang="lang" :post="false" @goHome="$emit('goHome')" @nav="$emit('nav')"/>
    <blogPosts :lang="lang"/>
  </div>

</template>

<script>
import blogWrappers from "../blog/blogWrappers";
import blogPosts from "../blog/blogPosts";


export default {
  name: "Blog",
  props:['slide', 'lang'],
  components:{
    blogWrappers,
    blogPosts,
  },
  emits:['goHome', 'nav', 'contact']
};
</script>

<style scoped>
</style>
