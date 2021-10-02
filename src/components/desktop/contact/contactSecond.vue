<template>
  <div>
    <div class="flex header">
      <div class="max-frai">
        <img src="@/assets/images/max-frai.svg" class="w-full" alt="" />
        <p
          class="uppercase inter font-bold mt-4 text-xxs"
          style="color: #ff2e53; letter-spacing: 1rem"
        >
          {{ text.AGENCY }}
        </p>
      </div>
      <div class="ml-27 h-full mt-auto">
        <div class="h-8px w-px" style="background: #ff2e53"></div>
      </div>
      <div class="ml-65 agency">
        <p
          class="font-medium text-base"
          @mouseover="agencyGradsOn"
          @mouseleave="agencyGradsOff"
        >
          {{ text.agency[0] }} <br />
          {{ text.agency[1] }}
        </p>
      </div>
      <div
        class="close ml-auto flex flex-col items-center cursor-pointer"
        @click="$emit('closeContacts')"
      >
        <p class="text-xxs uppercase" style="letter-spacing: 0.3rem">{{ text.close }}</p>
        <div class="close w-5 h-5 relative mt-4">
          <div
            class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 rotate-45"
            style="background: white"
          ></div>
          <div
            class="w-5 h-0.5 absolute left-1/2 top-1/2 transform -translate-x-1/2 -translate-y-1/2 -rotate-45"
            style="background: white"
          ></div>
        </div>
      </div>
    </div>
    <div class="mt-22.5">
      <div class="flex">
        <div class="flex flex-col">
          <h4 class="uppercase mb-6 text-xxl font-medium">
            {{ text.clicks }}
          </h4>
          <div
            class="chosen-services w-max flex items-center py-4 px-8 rounded-full border mb-3"
            v-for="item in services"
            :key="item.id"
          >
            <p class="cursor-default font-semibold text-xxsm uppercase">
              {{ item }}
            </p>
            <div
              class="ml-6 relative cursor-pointer"
              @click="deleteService(item)"
            >
              <div
                class="w-4 h-0.5 transform rotate-45 -translate-x-1/2 bg-white absolute"
              ></div>
              <div
                class="w-4 h-0.5 transform -rotate-45 -translate-x-1/2 bg-white absolute"
              ></div>
            </div>
          </div>
        </div>
        <div class="flex flex-col mt-0.25 ml-57">
          <div>
            <div class="field flex flex-col mb-8">
              <label for="name" class="text-xxsm font-semibold uppercase mb-2.5"
                >ИМЯ</label
              >
              <input v-model="name" id="name" type="text" class="w-185 h-15 pl-4" :class="{'error': activeErrors.indexOf(0) !== -1}" />
            </div>

            <div class="field flex flex-col mb-8">
              <label
                for="number"
                class="text-xxsm font-semibold uppercase mb-2.5"
                >ВАШ ТЕЛЕФОН</label
              >
              <input
                v-model="phone"
                id="number"
                @keydown.prevent="inputPhone($event)"
                :class="{'error': activeErrors.indexOf(1) !== -1 && activeErrors.indexOf(99) !== -1}"
                type="tel"
                class="w-185 h-15 pl-4"
              />
            </div>

            <div class="field flex flex-col mb-8">
              <label
                for="email"
                class="text-xxsm font-semibold uppercase mb-2.5"

                >EMAIL</label
              >
              <input
                @keypress.prevent="inputEmail($event)"
                v-model="email"
                id="email"
                type="email"
                class="w-185 h-15 pl-4"
                :class="{'error': activeErrors.indexOf(1) !== -1 && activeErrors.indexOf(88) !== -1}"
              />
            </div>

            <p class="text-lg" style="color: rgb(110, 117, 141)">
              Удобный формат общения
            </p>

            <div class="flex mt-6 w-full justify-between">
              <p
                @click="toggleFormat('phone')"
                :class="{ active: activeFormats.indexOf('phone') !== -1 }"
                class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border"
              >
                ЗВОНОК
              </p>
              <p
                @click="toggleFormat('email')"
                :class="{ active: activeFormats.indexOf('email') !== -1 }"
                class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border"
              >
                EMAIL
              </p>
              <p
                @click="toggleFormat('telegram')"
                :class="{ active: activeFormats.indexOf('telegram') !== -1 }"
                class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border"
              >
                Telegram
              </p>
              <p
                @click="toggleFormat('whatsapp')"
                :class="{ active: activeFormats.indexOf('whatsapp') !== -1 }"
                class="connection-format cursor-pointer font-semibold text-xxsm uppercase py-4 px-8 rounded-full border"
              >
                WHATSAPP
              </p>
            </div>


            <div class="mt-6 relative" style="z-index: 2;">
              <p class="mb-2 text-xs" style="color: rgba(255, 46, 83, 1)" v-for="error in activeErrors" :key="error.id">{{text.errors[error]}}</p>
            </div>
            <button
              @click="sendForm()"
              class="mt-19 become-client cursor-pointer"
              style="z-index: 2"
            >
              <div
                class="connect-content flex relative justify-start items-center"
                style="z-index: 2"
              >
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
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "contactSecond",
  props: ["choice"],
  emits: ["closeContacts"],
  data() {
    return {
      activeFormats: [],
      services: [],
      name: "",
      phone: "+38 (0__) ___ - __ - __",
      phoneIndexes:['+38 (0__) ___ - __ - __'],
      phoneActive:0,
      email: "",
      activeErrors: [],
    };
  },
  mounted() {
    this.services = this.choice;
  },
  methods: {
    deleteService(service) {
      if (this.services.length <= 1) {
        return;
      }
      this.services = this.services.filter((item) => item !== service);
    },
    sendForm() {
      this.activeErrors = []
      if (this.name === "") {
        this.activeErrors.push(0)
      }
      if (this.phone !== this.phoneIndexes[9]) {
        if (this.activeFormats.indexOf('phone') !== -1 || this.activeFormats.indexOf('telegram') !== -1 || this.activeFormats.indexOf('whatsapp') !== -1){
          this.activeErrors.push(1,99)
        }
      }
      if (this.email === "" || !/^(([^<>()\\[\]\\.,;:\s@"]+(\.[^<>()\\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/.test(this.email)){
        if (this.activeFormats.indexOf('email') !== -1){
          if (this.activeErrors.indexOf(1) === -1){
            this.activeErrors.push(1,88)
          } else{
            this.activeErrors.push(88)
          }

        }
      }
      if (this.phone !== this.phoneIndexes[9] && this.email === "" && this.activeErrors.indexOf(1) === -1){
        this.activeErrors.push(1,99,88)
      }
      if (this.activeFormats.length === 0){
        this.activeErrors.push(2)
      }
      if (this.activeErrors.length > 0){
        return
      }
    },
    inputPhone(e){
      if (e.key.match(/[0-9]/) && this.phoneIndexes.length < 10){
        this.phone = this.phone.replace("_", e.key);
        if (this.phoneIndexes.length < 9){
          this.phoneIndexes.push(this.phone)
        }
        return
      }
      if (e.key === 'Backspace'){
        if (this.phoneIndexes.length === 1){
          this.phone = this.phoneIndexes[0]
          return;
        }
        this.phone = this.phoneIndexes.pop()
      }

    },
    inputEmail(e){
      if (e.key.match(/[A-Za-z0-9@.]/)){
        this.email= this.email + e.key
      }
    },
    toggleFormat(format){
      if (this.activeFormats.indexOf(format) !== -1){
        this.activeFormats = this.activeFormats.filter(item => item !== format)
      } else {
        this.activeFormats.push(format)
      }
    }
  },
};
</script>

<style lang="scss" scoped>
input {
  background: rgba(2, 3, 6, 0.1);
  border: 0;
  border-bottom: 1px solid #6e758d;
}
input.error{
  border-bottom: 1px solid #f22959;
}
textarea:focus,
input:focus {
  outline: none;
}
.connection-format,
.chosen-services {
  transition: all 0.3s linear;
  border-color: rgba(151, 163, 203, 0.3);
}
.connection-format:hover {
  background: rgba(151, 163, 203, 0.5);
}
.connection-format.active {
  background: rgba(151, 163, 203, 0.5);
}
</style>
