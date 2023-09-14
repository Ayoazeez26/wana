<script setup lang="ts"></script>
<template>
  <div class="pt-20 px-4 xl:px-0 md:py-28 w-full">
    <img class="hidden lg:block" src="/img/hero-img.png" alt="video image" />
    <img class="lg:hidden" src="/img/hero-img-mob.png" alt="video image" />
    <div class="w-full max-w-[1240px] flex mx-auto mt-10 lg:mt-[68px]">
      <div
        class="flex flex-col justify-between lg:flex-row w-full max-w-[1240px]"
      >
        <h1
          class="font-semibold text-head leading-snug text-[38px] lg:leading-snug lg:text-[48px] w-full max-w-[403px]"
        >
          Welcome to Wana Services
        </h1>
        <div class="flex flex-col w-full max-w-[612px]">
          <p class="mt-4 lg:mt-0 leading-[28px] md:leading-[28px]">
            At Wana Services, we believe there is no place like home, and we are devoted to assisting you or your loved ones in maintaining independence and quality of life in the comfort of your home. Our purpose is to deliver compassionate and individualized care that is tailored to your specific requirements, allowing you to live life on your terms.
          </p>
          <div
            class="flex flex-col w-full lg:w-auto lg:flex-row lg:items-center gap-4 mt-10"
          >
            <nuxt-link
              to="/jobClient"
              class="bg-secondary text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-white"
            >
              Book Staff
            </nuxt-link>
            <nuxt-link
              to="/contact"
              class="bg-white text-center border-2 border-secondary font-semibold px-4 py-3 lg:w-[160px] rounded-lg text-secondary"
            >
              Contact Us
            </nuxt-link>
          </div>
        </div>
      </div>
    </div>
    <div class="w-full max-w-[1240px] flex mx-auto mt-20 md:mt-[120px]">
      <div
        class="flex flex-col justify-between lg:flex-row lg:items-center gap-10 w-full max-w-[1240px]"
      >
        <img class="w-full max-w-[612px]" src="/img/find.png" />
        <div class="flex flex-col w-full mt-10 md:mt-0 max-w-[572px]">
          <h2
            class="font-medium text-[26px] md:text-[32px] leading-[42px] md:leading-[48px]"
          >
            Our Range of In-Home Care Services
          </h2>
          <p class="mt-2 md:mt-6 leading-[28px] md:leading-[28px] ">
            With a staff of committed and professional carers, Wana Services provides a comprehensive range of in-home care services to clients of all ages and backgrounds. Our expert specialists are available to give the finest quality of care and support, whether you require assistance with everyday duties, medication management, companionship, or specialty care. We think that everyone deserves to age gracefully and with dignity, and our services are designed to help you or a loved one achieve that goal.
          </p>
        </div>
      </div>
    </div>
    <div class="w-full max-w-[1240px] flex mx-auto mt-20 md:mt-[120px]">
      <div
        class="flex flex-col justify-between lg:flex-row lg:items-center w-full max-w-[1240px]"
      >
        <div
          class="slide-parent border-l-4 flex flex-col w-full max-w-[572px] mb-10 md:mb-0"
        >
          <div class="slide-child w-full pl-6 py-4 -translate-x-1">
            <h2
              class="font-semibold text-lg md:text-xl leading-[34px] md:leading-[48px]"
            >
              Experienced and Qualified Staff
            </h2>
            <p class="mt-2 mb-3">
              Our dedicated team understands the importance of finding work in
              your city or town, and we are here to help you every step of the
              way.
            </p>
            <!-- <nuxt-link
              to="/jobCandidate"
              class="text-secondary font-bold py-2 text-sm"
              >Register as a Candidate
              <Icon name="mdi:arrow-right" size="20"></Icon
            ></nuxt-link> -->
          </div>
          <div class="w-full pl-6 py-4 -translate-x-1">
            <h2 class="font-semibold text-xl leading-[48px]">
              Talented Healthcare Professionals
            </h2>
            <p class="mt-2 mb-3">
              Schedule appointments with qualified healthcare providers to
              address your health concerns.
            </p>
            <!-- <nuxt-link
              to="/jobClient"
              class="text-secondary font-bold py-2 text-sm"
              >Book Staff <Icon name="mdi:arrow-right" size="20"></Icon
            ></nuxt-link> -->
          </div>
          <div class="w-full pl-6 py-4 -translate-x-1">
            <h2 class="font-semibold text-xl leading-[48px]">
              Home Help
            </h2>
            <p class="mt-2 mb-3">
              Our care professionals can provide support for general household activities and chores, giving you more time to rest.
            </p>
            <!-- <nuxt-link
              to="/applyNow"
              class="text-secondary font-bold py-2 text-sm"
              >Apply Now <Icon name="mdi:arrow-right" size="20"></Icon
            ></nuxt-link> -->
          </div>
        </div>
        <img class="w-full max-w-[612px]" src="/img/staff.png" />
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.slide-child {
  border-left: 4px solid #cb9821;
}
</style>
