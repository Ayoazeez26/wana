<template>
  <div class="fixed right-0 left-0 font-medium text-grey z-10 bg-white">
    <div
      class="flex h-24 md:h-[120px] items-center justify-between px-4 px-md-0 w-full max-w-[1240px] mx-auto"
    >
      <nuxt-link to="/">
        <img class="w-[89px]" src="/img/logo.png" />
      </nuxt-link>
      <button ref="hamburger" class="lg:hidden" @click="open = !open">
        <Icon name="ic:round-menu" size="24px" color="#1B5588" />
      </button>
      <div class="hidden lg:block relative">
        <ul
          class="hidden lg:flex flex-col lg:flex-row lg:items-center gap-4 mt-10 lg:mt-0 lg:gap-10"
        >
          <li @click="dataStore.job = false">
            <nuxt-link
              class="hover:text-secondary hover:font-semibold cursor-pointer"
              :class="
                route.name === 'index' ? 'text-secondary font-semibold' : ''
              "
              to="/"
              >Home</nuxt-link
            >
          </li>
          <li @click="dataStore.job = false">
            <nuxt-link
              class="hover:text-secondary hover:font-semibold cursor-pointer"
              :class="
                route.name === 'about' ? 'text-secondary font-semibold' : ''
              "
              to="/about"
              >About Us</nuxt-link
            >
          </li>
          <li @click="dataStore.job = false">
            <nuxt-link
              class="hover:text-secondary hover:font-semibold cursor-pointer"
              :class="
                route.name === 'service' ? 'text-secondary font-semibold' : ''
              "
              to="/service"
              >Services</nuxt-link
            >
          </li>
          <!-- <li @click="jobToggled">
            <p
              class="hover:text-secondary hover:font-semibold cursor-pointer"
              :class="
                route.name === 'jobCandidate' ||
                route.name === 'jobClient' ||
                route.name === 'applyNow'
                  ? 'text-secondary font-semibold'
                  : ''
              "
            >
              Find Jobs<Icon
                name="ic:round-keyboard-arrow-down"
                size="24px"
                color="#5A5A59"
              />
            </p>
          </li> -->
        </ul>
        <!-- <JobDropdown
          class="absolute hidden lg:block top-20 right-0"
          v-if="dataStore.job"
        /> -->
      </div>
      <ul
        class="navbar-links flex items-start"
        :class="{ 'navbar-links--navopen overflow-y-auto pb-8': open }"
        v-click-outside="close"
      >
        <div
          class="hidden lg:flex flex-col w-full lg:w-auto lg:flex-row lg:items-center gap-4"
        >
          <nuxt-link
            to="/contact"
            class="bg-secondary text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-white"
          >
            Contact Us
          </nuxt-link>
          <!-- <nuxt-link
            to="/jobClient"
            class="bg-secondary text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-white"
          >
            Book Staff
          </nuxt-link> -->
        </div>
        <div class="flex w-full mt-3 lg:hidden justify-between items-center">
          <nuxt-link to="/">
            <img class="w-[102px]" src="/img/logo.png" />
          </nuxt-link>
          <button class="" @click="open = !open">
            <Icon name="ic:round-close" size="24px" color="#1B5588" />
          </button>
        </div>
        <ul
          class="flex lg:hidden flex-col lg:flex-row lg:items-center w-full gap-4 mt-10 lg:mt-0 lg:gap-10"
        >
          <li class="cursor-pointer py-3" @click="open = !open">
            <nuxt-link to="/">Home</nuxt-link>
          </li>
          <li class="cursor-pointer py-3" @click="open = !open">
            <nuxt-link to="/about">About Us</nuxt-link>
          </li>
          <li class="cursor-pointer py-3" @click="open = !open">
            <nuxt-link to="/service"
              >Services<Icon
                name="ic:round-keyboard-arrow-down"
                size="24px"
                color="#FFFFFF"
            /></nuxt-link>
          </li>
          <!-- <li class="cursor-pointer py-3" @click="jobToggled">
            <p>Find Jobs</p>
          </li>
          <JobDropdown class="lg:hidden" v-if="dataStore.job" /> -->
          <div
            class="flex flex-col w-full lg:w-auto lg:flex-row lg:items-center gap-4"
          >
            <nuxt-link
              to="/contact"
              class="bg-secondary text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-white"
            >
              Contact Us
            </nuxt-link>
            <!-- <nuxt-link
              to="/jobClient"
              class="bg-secondary text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-white"
            >
              Book Staff
            </nuxt-link> -->
          </div>
        </ul>
      </ul>
    </div>
  </div>
</template>

<script setup lang="ts">
import { useDataStore } from "@/stores/data";
const dataStore = useDataStore();
const route = useRoute();
console.log(route.name);
const scrolled = ref(false);
const open = ref(false);
const close = (e: HTMLInputElement) => {
  if (e.target.tagName !== "svg" && e.target.tagName !== "path") {
    open.value = false;
  }
};

const handleScroll = () => {
  scrolled.value = window.scrollY > 0;
};

const jobToggled = () => {
  dataStore.job = !dataStore.job;
};

if (typeof window !== "undefined") {
  window.addEventListener("scroll", handleScroll);
}
</script>

<style lang="scss" scoped>
.navbar {
  &-links {
    display: flex;
    // align-items: center;
    list-style-type: none;

    &__item {
      margin: 0;
      a:not([data-type="button"]) {
        color: $primary;
        text-decoration: none;
        &:hover {
          opacity: 0.9;
          color: $primary;
        }
        @media screen and (min-width: 768px) {
          padding-left: 15px;
          padding-right: 15px;
        }
        &.drop {
          color: $primary;
          padding: 0;
        }
      }

      // button:not([data-type=button]) {
      //   color: $black;
      //   font-weight: 700;
      //   border-radius: 8px;
      //   min-height: 50px;
      //   min-width: 170px;
      // }
    }

    &__city {
      width: 300px;
    }
    &__about {
      width: 260px;
    }

    @media screen and (max-width: 1023px) {
      transform: translateX(500px);
      // pointer-events: none;
      position: fixed;
      transition: transform 0.2s ease-out;
      display: flex;
      flex-direction: column;
      padding-top: 20px;
      padding-left: 20px !important;
      padding-right: 20px;
      top: 0;
      bottom: 0;
      right: 0;
      width: 500px;
      max-width: 100vw;
      background-color: white;
      z-index: 100;
      &__toggle {
        display: none;
      }
      &--navopen {
        transform: translateX(0);
        pointer-events: all;

        .navbar-links__toggle {
          display: block;
          position: fixed;
          top: 50px;
          right: 20px;
          background: none;
          border: none;
        }

        .navbar-links__item {
          text-align: left;
          margin: 20px 0;
          width: 100%;

          .btn {
            width: 100%;
          }
        }
      }
    }
  }

  &__toggle {
    background: none;
    border: none;

    div {
      background-color: $black;
      height: 3px;
      border-radius: 2px;
      margin: 4px;
      &:nth-child(2) {
        width: 20px;
      }

      &:nth-child(3) {
        width: 15px;
      }

      &:last-child {
        width: 9px;
      }
    }
  }
  &-scroll {
    box-shadow: 1px 2px 18px rgba(255, 255, 255, 0.1);
    background-color: $grey-2 !important;
    // background-color: transparent !important;
  }
}
</style>
