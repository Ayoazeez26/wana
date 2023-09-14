<script setup lang="ts">
const services = ref([
  {
    img: "care",
    name: "Health Care Assistance",
  },
  {
    img: "carers",
    name: "Carers",
  },
]);
const breakpoints = ref({
  150: {
    itemsToShow: 1,
    snapAlign: "center",
  },
  1000: {
    itemsToShow: 2,
    snapAlign: "center",
  },
});

const carousel = ref(null);
const next = () => {
  carousel.value.next();
};

const prev = () => {
  carousel.value.prev();
};
</script>
<template>
  <div class="w-full pt-[80px] lg:pt-[64px]">
    <div class="flex flex-col mx-auto w-full max-w-[1240px]">
      <div class="w-full flex flex-col items-center text-center px-4">
        <div class="w-full mb-14 max-w-[434px]">
          <h2 class="text-2xl lg:text-[32px] font-semibold mb-4">What We Do</h2>
          <!-- <p>
            You can Recruit or Become Nurse, Care Assistants, Support Workers,
            and Social Workers
          </p> -->
        </div>
        <div class="w-full text-left">
          <div
            class="flex flex-col justify-between lg:flex-row lg:items-center gap-10 w-full max-w-[1240px]"
          >
            <img class="w-full max-w-[612px]" src="/img/about.png" />
            <div class="flex flex-col w-full mt-10 md:mt-0 max-w-[572px]">
              <h2
                class="font-medium text-[26px] md:text-2xl leading-[42px] md:leading-[40px]"
              >
                Domiciliary Care
              </h2>
              <p class="mt-2 leading-[28px] md:leading-[28px]">
                Treasure Vince Care offers high-quality domiciliary care that
                helps people live independently in their own homes. Caregivers
                work with each individual to create a personalized care plan
                that meets their unique needs and goals. Service users are also
                given opportunities to participate in the development and review
                of their care plans, so they have a say in how they are cared
                for.
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div id="about" />
  </div>
</template>

<style lang="scss"></style>
