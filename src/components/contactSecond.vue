<template>
<div>
  <div class="flex header">
    <div class="max-frai">
      <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
      <p
        class="uppercase inter font-bold mt-4 text-xxs"
        style="color: #ff2e53; letter-spacing: 1rem;"
      >
        AGENCY
      </p>
    </div>
    <div class="ml-27 h-full mt-auto">
      <div class="h-8px w-px" style="background: #ff2e53"></div>
    </div>
    <div class="ml-65 agency">
      <p class="font-medium text-base" @mouseover="agencyGradsOn" @mouseleave="agencyGradsOff">
        Агентство простых решений сложного <br />
        цифрового мира
      </p>
    </div>
    <div class="close ml-auto flex flex-col items-center cursor-pointer" @click="$emit('closeContacts')">
      <p class="text-xxs uppercase" style="letter-spacing: 0.3rem">close</p>
      <div class="close w-5 h-5 relative mt-4" >
        <div class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-45" style="background:white;"></div>
        <div class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 -rotate-45" style="background:white;"></div>
      </div>
    </div>
  </div>
  <div class="mt-22.5">
    <div class="flex">
      <div class="flex flex-col">
        <h4 class="uppercase mb-6 text-xxl font-medium">Решение в пару кликов</h4>
        <div class="connection-format  w-max flex items-center py-4 px-8 rounded-full border"><p class="font-semibold text-xxsm uppercase">{{choice}}</p> <div class="ml-6 relative cursor-pointer"><div class="w-4 h-0.5 transform rotate-45 -translate-x-1/2 bg-white absolute"></div><div class="w-4 h-0.5 transform -rotate-45 -translate-x-1/2 bg-white absolute"></div></div></div>
      </div>
      <div class="flex flex-col mt-0.25 ml-57">
        <form action="">
          <div class="field flex flex-col mb-8">
            <label for="name" class="text-xxsm font-semibold uppercase mb-2.5">ИМЯ</label>
            <input id="name" type="text" class="w-185 h-15">
          </div>
          <div class="field flex flex-col mb-8">
            <label for="number" class="text-xxsm font-semibold uppercase mb-2.5">ВАШ ТЕЛЕФОН</label>
            <input id="number" type="tel" class="w-185 h-15">
          </div>
          <div class="field flex flex-col mb-8">
            <label for="email" class="text-xxsm font-semibold uppercase mb-2.5">EMAIL</label>
            <input id="email" type="email" class="w-185 h-15">
          </div>
          <p class="text-lg" style="color: rgb(110,117,141)">Удобный формат общения</p>
          <div class="flex mt-6 w-full justify-between mb-25">
            <p @click="activeFormat = 'phone'" :class="{'active': activeFormat === 'phone'}" class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border">ТЕЛЕФОН</p>
            <p @click="activeFormat = 'email'" :class="{'active': activeFormat === 'email'}" class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border">EMAIL</p>
            <p @click="activeFormat = 'telegram'" :class="{'active': activeFormat === 'telegram'}" class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border">Telegram</p>
            <p @click="activeFormat = 'whatsapp'" :class="{'active': activeFormat === 'whatsapp'}" class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border">WHATSAPP</p>
          </div>
          <button type="submit" class="mt-auto become-client cursor-pointer" style="z-index: 2">
            <div class="connect-content flex relative justify-start items-center" style="z-index: 2">
              <div class="plus w-12.5 h-12.5 rounded-full mr-5 relative">
                <div
                  class="absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                ></div>
                <div
                  class="absolute top-1/2 left-1/2 transform rotate-90 -translate-x-1/2 -translate-y-1/2 w-4 h-2px"
                ></div>
              </div>
              <p class="uppercase font-semibold text-xxsm">отправить</p>
            </div>
            <div class="connect-grad relative" style="z-index: 1">
              <div id="grad-1"></div>
              <div id="grad-2"></div>
              <div id="grad-3"></div>
            </div>
          </button>
        </form>

      </div>
    </div>


  </div>
</div>
</template>
<script>
export default {
  name: "contactSecond",
  props:['choice'],
  emits:['closeContacts'],
  data(){
    return{
      activeFormat:''
    }
  }
};
</script>

<style lang="scss" scoped>
input{
  background: rgba(2, 3, 6, 0.1);
  border: 0;
  border-bottom: 1px solid #6E758D;
}
textarea:focus, input:focus{
  outline: none;
}
.connection-format{
  transition: all .3s linear;
  border-color: rgba(151, 163, 203, 0.3);
}
.connection-format:hover{
  background: rgba(151, 163, 203, 0.5);
}
.connection-format.active{
  background: rgba(151, 163, 203, 0.5);
}
</style>
