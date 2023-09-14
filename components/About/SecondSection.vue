<script setup lang="ts">
const services = ref(["surrey", "agri", "anchor", "trust", "point"]);

const carousel = ref(null);
const next = () => {
  carousel.value.next();
};

const prev = () => {
  carousel.value.prev();
};
const breakpoints = ref({
  150: {
    itemsToShow: 2,
    snapAlign: "center",
  },
  768: {
    itemsToShow: 3,
    snapAlign: "center",
  },
  1000: {
    itemsToShow: 5,
    snapAlign: "center",
  },
});
</script>
<template>
  <div class="py-20 px-4 xl:px-0 md:py-28 w-full max-w-[1240px] mx-auto">
    <div class="w-full flex mx-auto">
      <div
        class="flex flex-col justify-between gap-10 lg:flex-row lg:items-center w-full max-w-[1240px]"
      >
        <img class="w-full max-w-[612px]" src="/img/medicals.png" />
        <div class="flex flex-col w-full mt-10 md:mt-0 max-w-[572px]">
          <h2
            class="font-medium text-[26px] md:text-[32px] leading-[42px] md:leading-[48px]"
          >
            Our Mission
          </h2>
          <p class="mt-2 leading-[28px]">
            Our mission at Wana Healthcare & Services is to provide high-quality
            domiciliary care services that allow people to age gracefully and
            with dignity in the comfort of their own homes. We are passionately
            devoted to developing independence and improving our client's
            quality of life. Our caring staff works hard to fulfill every need
            of each person we serve, ensuring that they receive the
            compassionate and personalized attention they deserve.
          </p>
        </div>
      </div>
    </div>
    <div class="w-full pt-16">
      <p class="text-center">We are trusted by amazing companies</p>
      <Carousel ref="carousel" :breakpoints="breakpoints" class="w-full">
        <Slide v-for="(service, index) in services" :key="index">
          <div class="carousel__item h-14">
            <img class="h-14 w-auto" :src="`/img/${service}.png`" alt="" />
          </div>
        </Slide>
        <template #addons>
          <Navigation class="invisible md:visible" />
        </template>
      </Carousel>
      <div class="flex md:hidden gap-6 justify-center">
        <button
          @click="prev"
          class="flex min-w-max bg-white border border-grey-3 w-16 h-16 rounded-lg items-center justify-center mt-2"
        >
          <Icon name="mdi:arrow-left" size="32" />
        </button>
        <button
          @click="next"
          class="flex min-w-max bg-white border border-grey-3 w-16 h-16 rounded-lg items-center justify-center mt-2"
        >
          <Icon name="mdi:arrow-right" size="32" />
        </button>
      </div>
    </div>
    <div
      class="flex flex-col lg:flex-row lg:justify-between w-full mt-16 md:mt-10"
    >
      <h2
        class="font-medium text-[26px] md:text-[32px] leading-[42px] md:leading-[48px]"
      >
        Why Choose Wana Healthcare & Services
      </h2>
      <p class="mt-6 md:mt-0 leading-[28px] w-full max-w-[612px]">
        What distinguishes Wana Healthcare & Services is our unrelenting
        dedication to our client's well-being. We make meaningful connections
        and improve lives in addition to delivering necessary care services.
        Wana Healthcare & Services is your trusted partner in attaining the
        finest quality of life at home, with a track record of excellence, a
        team of caring experts, and a client-centered approach. We are your best
        choice for in-home care that puts your comfort, safety, and happiness
        first.
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.slide-child {
  border-left: 4px solid #cb9821;
}
</style>
