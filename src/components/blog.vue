<template>
  <div class="blog relative overflow-scroll" id="blog" @wheel.stop>
    <blogWrappers @blog="post = false" :post="post" @goHome="$emit('goHome')" @nav="$emit('nav')"/>
    <post v-if="post"/>
    <blogPosts v-else/>
  </div>

</template>

<script>
import blogWrappers from "./blog/blogWrappers";
import blogPosts from "./blog/blogPosts";
import post from "./blog/post";


export default {
  name: "Blog",
  props:['slide'],
  components:{
    blogWrappers,
    blogPosts,
    post
  },
  data(){
    return{
      post:true
    }
  },
  emits:['goHome', 'nav', 'contact']
};
</script>

<style scoped>
</style>
