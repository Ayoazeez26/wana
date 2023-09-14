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
    <div
      class="flex flex-col lg:flex-row lg:justify-between w-full mt-16 md:mt-10"
    >
      <h2
        class="font-medium text-[26px] md:text-[32px] leading-[42px] md:leading-[48px]"
      >
        Our Commitment to Excellence
      </h2>
      <p class="mt-6 md:mt-0 leading-[28px] w-full max-w-[612px]">
        Wana Services is committed to consistently improving the quality of our
        domiciliary care services. We remain up to date on the newest
        developments in the field, ensuring that our services are not only
        compassionate but also based on the greatest healthcare practices. Our
        dedication to quality extends to our caregivers' continual training and
        professional development, allowing them to deliver the greatest level of
        care and assistance to our clients. Our staff are dedicated to exceeding
        your expectations and enhancing your life via tailored, top-tier
        domiciliary care.
      </p>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.slide-child {
  border-left: 4px solid #cb9821;
}
</style>
