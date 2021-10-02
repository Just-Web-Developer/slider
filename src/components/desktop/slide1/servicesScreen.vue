<template>
  <div class="mt-45 relative w-200 h-67.5 services" style="z-index: 100;" :class="servicesClass">

    <div
      id="first-service"
      @mouseover="servicesClass = 'first-state'"
      @mouseleave="servicesClass = 'null-state'"
      class="absolute service"
    >
      <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
        <transition name="service-count">
          <span
            v-if="servicesClass !== 'first-state'"
            class="absolute top-0 left-0"
            >01</span
          >
        </transition>
        <p
          class="font-medium text-white uppercase ml-0 service-name"
          :class="
            servicesClass === 'first-state'
              ? 'ml-100p transform -translate-x-full'
              : ''
          "
        >
          {{ text[0].title }}
        </p>
        <transition name="service-hover-screen">
          <div
            v-if="servicesClass === 'first-state'"
            class="absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5 flex flex-col justify-between"
          >
            <div class="flex justify-between">
              <img
                v-if="servicesClass === 'first-state'"
                src="@/assets/images/slide_1/service_icons/loader.svg"
                class="icon h-10"
                alt=""
              />
              <p class="service-name font-medium text-white uppercase">
                {{ text[0].title }}
              </p>
            </div>
            <div
              class="flex flex-col items-end absolute right-7.5 bottom-7.5 service-list first-text"
            >
              <p class="text-left service-items">
                {{text[0].points[0]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[0].points[1]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[0].points[2]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
            </div>
          </div>
        </transition>
      </div>
    </div>

    <div
      id="second-service"
      @mouseover="servicesClass = 'second-state'"
      @mouseleave="servicesClass = 'null-state'"
      class="absolute service"
    >
      <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
        <transition name="service-count">
          <span
            v-if="servicesClass !== 'second-state'"
            class="absolute top-0 left-0"
            >02</span
          >
        </transition>
        <p
          class="font-medium text-white uppercase ml-0 service-name"
          :class="
            servicesClass === 'second-state'
              ? 'ml-100p transform -translate-x-full'
              : ''
          "
        >
          {{ text[1].title }}
        </p>
        <transition name="service-hover-screen">
          <div
            v-if="servicesClass === 'second-state'"
            class="absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5 flex flex-col justify-between"
          >
            <div class="flex justify-between">
              <img
                v-if="servicesClass === 'second-state'"
                src="@/assets/images/slide_1/service_icons/globe.svg"
                class="icon h-10"
                alt=""
              />
              <p class="service-name font-medium text-white uppercase">{{ text[1].title }}</p>
            </div>
            <div
              class="flex flex-col items-end absolute right-7.5 bottom-7.5 service-list second-text"
            >
              <p class="text-left service-items">
                {{text[1].points[0]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[1].points[1]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[1].points[2]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
            </div>
          </div>
        </transition>
      </div>
    </div>

    <div
      id="third-service"
      @mouseover="servicesClass = 'third-state'"
      @mouseleave="servicesClass = 'null-state'"
      class="absolute service"
    >
      <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
        <transition name="service-count">
          <span
            v-if="servicesClass !== 'third-state'"
            class="absolute top-0 left-0"
            >03</span
          >
        </transition>
        <p
          class="font-medium text-white uppercase ml-0 service-name"
          :class="
            servicesClass === 'third-state'
              ? 'ml-100p transform -translate-x-full'
              : ''
          "
        >
          {{text[2].title}}
        </p>
        <transition name="service-hover-screen">
          <div
            v-if="servicesClass === 'third-state'"
            class="absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5 flex flex-col justify-between"
          >
            <div class="flex justify-between">
              <img
                v-if="servicesClass === 'third-state'"
                src="@/assets/images/slide_1/service_icons/radio.svg"
                class="icon h-10"
                alt=""
              />
              <p class="service-name font-medium text-white uppercase">
                {{text[2].title}}
              </p>
            </div>
            <div
              class="flex flex-col items-end absolute right-7.5 bottom-7.5 service-list third-text"
            >
              <p class="text-left service-items">
                {{text[2].points[0]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[2].points[1]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[2].points[2]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
            </div>
          </div>
        </transition>
      </div>
    </div>

    <div
      id="fourth-service"
      @mouseover="servicesClass = 'fourth-state'"
      @mouseleave="servicesClass = 'null-state'"
      class="absolute service"
    >
      <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
        <transition name="service-count">
          <span
            v-if="servicesClass !== 'fourth-state'"
            class="absolute top-0 left-0"
            >04</span
          >
        </transition>
        <p
          class="font-medium text-white uppercase ml-0 service-name"
          :class="
            servicesClass === 'fourth-state'
              ? 'ml-100p transform -translate-x-full'
              : ''
          "
        >
          {{text[3].title}}
        </p>
        <transition name="service-hover-screen">
          <div
            v-if="servicesClass === 'fourth-state'"
            class="absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5 flex flex-col justify-between"
          >
            <div class="flex justify-between">
              <img
                v-if="servicesClass === 'fourth-state'"
                src="@/assets/images/slide_1/service_icons/pen-tool.svg"
                class="icon h-10"
                alt=""
              />
              <p class="service-name font-medium text-white uppercase">{{text[3].title}}</p>
            </div>
            <div
              class="flex flex-col items-end absolute right-7.5 bottom-7.5 service-list fourth-text"
            >
              <p class="text-left service-items">
                {{text[3].points[0]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[3].points[1]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
              <p class="text-left service-items">
                {{text[3].points[2]}}
                <img
                  src="@/assets/images/slide_1/service_icons/cross.svg"
                  class="inline ml-4"
                  alt=""
                />
              </p>
            </div>
          </div>
        </transition>
      </div>
    </div>

    <div
      id="fifth-service"
      @mouseover="servicesClass = 'fifth-state'"
      @mouseleave="servicesClass = 'null-state'"
      class="absolute service"
    >
      <div class="relative flex pt-7.5 pr-7.5 h-full overflow-hidden label">
        <transition name="service-count">
          <span
            v-if="servicesClass !== 'fifth-state'"
            class="absolute top-0 left-0"
            >05</span
          >
        </transition>
        <p
          class="font-medium text-white uppercase ml-0 service-name"
          :class="
            servicesClass === 'fifth-state'
              ? 'ml-100p transform -translate-x-full'
              : ''
          "
        >
          {{text[4].title}}
        </p>
        <transition name="service-hover-screen">
          <div
            v-if="servicesClass === 'fifth-state'"
            class="absolute top-0 left-0 right-0 bottom-0 hover-screen p-7.5 flex flex-col justify-between"
          >
            <div class="flex justify-between">
              <img
                v-if="servicesClass === 'fifth-state'"
                src="@/assets/images/slide_1/service_icons/smile.svg"
                class="icon h-10"
                alt=""
              />
              <p class="service-name font-medium text-white uppercase">
                {{text[4].title}}
              </p>
            </div>
            <div
              class="flex flex-col items-end absolute right-7.5 bottom-7.5 service-list fifth-text"
            >
              <p style="line-height: 1.9375rem">{{text[4].points[0]}}</p>
              <p style="line-height: 1.9375rem">{{text[4].points[1]}}</p>
            </div>
          </div>
        </transition>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "servicesScreen",
  data() {
    return {
      servicesClass: "first-state",
    };
  },
  props:['text']
};
</script>

<style lang="scss" scoped>
.service{
  z-index: 20;
}
.services {
  .icon {
    transform: translateY(-0%) rotate(0deg);
  }
  & > div {
    transition: all 0.35s ease-out;
    .label {
      .service-name {
        font-size: 1.25rem;
        line-height: 2.5rem;
        transition: all 0.35s ease-out;
      }
      .service-items {
        line-height: 2.5rem;
        font-size: 1.0625rem;
      }
      span {
        color: rgba(151, 163, 203, 0.6);
        font-size: 0.625rem;
        line-height: 0.625rem;
      }
    }
    .hover-screen {
      background: rgba(23, 26, 31, 1);
      z-index: -1;
    }
  }
}
.services.null-state {
  & > div {
    width: 33.3%;
    height: 50%;
  }
  #first-service {
    top: 0;
    left: 0;
  }
  #second-service {
    top: 0;
    left: 33.3%;
  }
  #third-service {
    top: 0;
    left: 66.6%;
  }
  #fourth-service {
    top: 50%;
    left: 33.3%;
  }
  #fifth-service {
    top: 50%;
    left: 66.6%;
  }
}

.services.first-state {
  & > div {
    transition: all 0.35s ease-out;
  }
  #first-service {
    top: 0;
    left: 0;
    height: 100%;
    width: 40%;
  }
  #second-service {
    top: 0;
    left: 46.6%;
    height: 33.3%;
    width: 20%;
  }
  #third-service {
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service {
    top: 33.3%;
    left: 46.6%;
    height: 33.3%;
    width: 20%;
  }
  #fifth-service {
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #second-service .label > p,
  #third-service .label > p,
  #fourth-service .label > p,
  #fifth-service .label > p {
    font-size: 1rem;
    color: rgba(151, 163, 203, 0.6);
  }
}

.services.second-state {
  & > div {
    transition: all 0.35s ease-out;
  }
  #first-service {
    top: 0;
    left: 0;
    height: 33.3%;
    width: 20%;
  }
  #second-service {
    top: 0;
    left: 20%;
    height: 100%;
    width: 40%;
  }
  #third-service {
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service {
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fifth-service {
    top: 66.6%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #first-service .label > p,
  #third-service .label > p,
  #fourth-service .label > p,
  #fifth-service .label > p {
    font-size: 1rem;
    color: rgba(151, 163, 203, 0.6);
  }
}

.services.third-state {
  & > div {
    transition: all 0.35s ease-out;
  }
  #first-service {
    top: 0;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #second-service {
    top: 0;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #third-service {
    top: 0;
    left: 56.6%;
    height: 100%;
    width: 40%;
  }
  #fourth-service {
    top: 33.3%;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #fifth-service {
    top: 33.3%;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #second-service .label > p,
  #first-service .label > p,
  #fourth-service .label > p,
  #fifth-service .label > p {
    font-size: 1rem;
    color: rgba(151, 163, 203, 0.6);
  }
}

.services.fourth-state {
  & > div {
    transition: all 0.35s ease-out;
  }
  #first-service {
    top: 0;
    left: 0;
    height: 33.3%;
    width: 20%;
  }
  #second-service {
    top: 33.3%;
    left: 0;
    height: 33.3%;
    width: 20%;
  }
  #third-service {
    top: 0;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #fourth-service {
    top: 0;
    left: 20%;
    height: 100%;
    width: 40%;
  }
  #fifth-service {
    top: 33.3%;
    left: 66.6%;
    height: 33.3%;
    width: 20%;
  }
  #second-service .label > p,
  #third-service .label > p,
  #first-service .label > p,
  #fifth-service .label > p {
    font-size: 1rem;
    color: rgba(151, 163, 203, 0.6);
  }
}

.services.fifth-state {
  & > div {
    transition: all 0.35s ease-out;
  }
  #first-service {
    top: 0;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #second-service {
    top: 0;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #third-service {
    top: 33.3%;
    left: 25%;
    height: 33.3%;
    width: 25%;
  }
  #fourth-service {
    top: 33.3%;
    left: 0;
    height: 33.3%;
    width: 25%;
  }
  #fifth-service {
    top: 0;
    left: 56.6%;
    height: 100%;
    width: 40%;
  }
  #second-service .label > p,
  #third-service .label > p,
  #fourth-service .label > p,
  #first-service .label > p {
    font-size: 1rem;
    color: rgba(151, 163, 203, 0.6);
  }
}

.service-count-enter-active,
.service-count-leave-active,
.service-hover-screen-enter-active,
.service-hover-screen-leave-active {
  transition: all 0.35s ease-out;
  .icon {
    transition: all 0.35s ease-out;
  }
  .first-text,
  .second-text,
  .third-text,
  .fourth-text,
  .fifth-text {
    transition: all 0.35s ease-out;
  }
}

.service-count-enter-from,
.service-count-leave-to {
  transform: translateX(300%);
  opacity: 0;
}

.service-hover-screen-enter-from,
.service-hover-screen-leave-to {
  transform: translateX(-100%);
  opacity: 0;
  .icon {
    transform: translateY(-0%) rotate(360deg);
  }
  .first-text {
    right: -100%;
    bottom: -150%;
  }
  .second-text {
    right: -100%;
    bottom: -150%;
  }
  .third-text {
    right: -100%;
    bottom: -150%;
  }
  .fourth-text {
    right: -100%;
    bottom: -150%;
  }
  .fifth-text {
    right: -100%;
    bottom: -150%;
  }
}
</style>
