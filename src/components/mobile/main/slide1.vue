<template>
  <div style="color: white; margin-top: 50vh">


<!--    First section START-->

      <slider></slider>

    <!--    Second section END-->

  </div>

</template>

<script>
import slider from "../reuseable/slider";

export default {
  name: "slide1",
  components:{slider}
};
</script>

<style scoped lang="scss">
  .service-m{
    background: rgba(110, 117, 141, 0.1);
  }
  .dop{
    transition: all 0.35s ease-out;
  }
  .slide-2{
    .header{
      .icons{
        svg{
          width: 2.5rem;
        }
      }
    }
  }
</style>