<template>
  <div class="agency fixed left-8p" :class="{'active': agency, 'hover': state !==7 }">
    <div class="purple"></div>
    <div class="blue"></div>
  </div>
</template>

<script>
export default {
  name: "WrapGrads",
  props: ['agency', 'state']
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
    width: 28.75rem;
    height: 28.75rem;
    left: 35.9375rem;
    top: -17.603125rem;
    z-index: 2;
    background: linear-gradient(321.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(242, 41, 89, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(3.75rem);
    transform: rotate(-22.14deg);
  }
  .blue {
    position: absolute;
    width: 28.75rem;
    height: 28.75rem;
    left: 44.67125rem;
    top: -13.019375rem;
    background: linear-gradient(344.88deg, rgba(7, 25, 61, 0) 12.53%, rgba(0, 133, 255, 0.4) 43.45%, rgba(255, 0, 0, 0.4) 60.5%);
    filter: blur(3.75rem);
    transform: rotate(-22.14deg);
  }
  .blue, .purple{
    transition: all .8s linear;
  }
}
.agency.active{
  transform: scale(.9);
  left: 15%;
  top: -10%;
  .purple{
    width: 40.93875rem;
    height: 40.93875rem;
    left: 19.875rem;
    top: -19.635rem;
  }
  .blue{
    width: 40.93875rem;
    height: 40.93875rem;
    left: 43.31125rem;
    top: -13.108125rem;
  }
}
.agency.hover{
  .blue, .purple{
    z-index: -10;
    transition: all .3s linear;
  }
}
</style>
