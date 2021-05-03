<template>
  <div class="agency fixed left-8p z-10">
  <div class="purple"></div>
  <div class="blue"></div>
</div>
</template>

<script>
export default {
  name: "WrapGrads"
};
</script>

<style lang="scss" scoped>
.agency {

  transition: all 1s linear;
  top: -8%;
  div{
    border-radius: 50%;
  }
  .purple {
    position: absolute;
    width: 460px;
    height: 460px;
    left: 575px;
    top: -281.65px;
    z-index: 2;
    background: linear-gradient(321.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(242, 41, 89, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(60px);
    transform: rotate(-22.14deg);
    transition: all .2s linear;
  }
  .blue {
    position: absolute;
    width: 460px;
    height: 460px;
    left: 714.74px;
    top: -208.31px;
    background: linear-gradient(344.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(0, 133, 255, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(60px);
    transform: rotate(-22.14deg);
    transition: all .2s linear;
  }
}
.agency:hover{
  top: -10%;
  .purple{
    width: 655.02px;
    height: 655.02px;
    left: 318px;
    top: -314.16px;
  }
  .blue{
    width: 655.02px;
    height: 655.02px;
    left: 692.98px;
    top: -209.73px;
  }
}
</style>
