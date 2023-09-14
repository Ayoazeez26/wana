<script setup lang="ts">
const values = ref([
  {
    title: "Home Care",
    desc: "From simple housekeeping to companionship, personal care and healthcare, we always offer the personal touch.",
  },
  {
    title: "Enhanced Care",
    desc: "Combining our award winning care with technology to enhance our client’s lives.",
  },
  {
    title: "Overnight Care",
    desc: "When your loved one requires care overnight, our trained care professionals can be on hand to provide support - whether this means having someone simply sleeping in the next room, or being awake and directly on hand to assist with any care needs",
  },
  {
    title: "Home Help",
    desc: "Our care professionals can provide support for general household activities and chores, giving you more time to rest.",
  },
  {
    title: "Daytime Care",
    desc: "Our care professionals are able to provide tailored support during the day when loved ones are at work or unable to provide care.",
  },
  {
    title: "Respite Care",
    desc: "At Wana we understand it’s important that family caring for their loved ones take a rest from time to time, which is where our respite care at home service can help.",
  },
]);
</script>
<template>
  <div class="bg-grey-5 px-4 xl:px-0 py-14 md:py-[120px] w-full">
    <div class="w-full max-w-[1240px] flex mx-auto">
      <div
        class="flex flex-col md:flex-row items-center md:items-start justify-center w-full max-w-[1240px]"
      >
        <div
          class="flex flex-col text-center md:text-left w-full md:max-w-[320px]"
        >
          <h1
            class="font-medium text-head leading-snug text-[28px] lg:leading-snug lg:text-[32px] w-full max-w-[572px]"
          >
            The Other Services We Provide
          </h1>
        </div>
        <div class="mt-14 md:mt-0 flex gap-8 justify-center items-start flex-wrap w-full">
          <div class="flex flex-col gap-8">
            <template v-for="(value, index) in values">
              <div v-if="index % 2 === 0" :key="index" class="card py-16 px-6 gap-2 w-full max-w-[424px]">
                <p class="text-head text-lg font-semibold leading-[34px]">
                  {{ value.title }}
                </p>
                <p class="leading-[28px] text-left">{{ value.desc }}</p>
              </div>
            </template>
          </div>
          <div class="flex flex-col gap-8 lg:mt-8">
            <template v-for="(value, index) in values">
              <div v-if="index % 2 !== 0" :key="index" class="card py-16 px-6 gap-2 w-full max-w-[424px]">
                <p class="text-head text-lg font-semibold leading-[34px]">
                  {{ value.title }}
                </p>
                <p class="leading-[28px] text-left">{{ value.desc }}</p>
              </div>
            </template>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.card {
  background: #fff;
  box-shadow: 0px 2px 16px 0px rgba(0, 0, 0, 0.08);
  display: flex;
  // width: 397.333px;
  // height: 234px;
  // padding: 32px 24px;
  flex-direction: column;
  align-items: flex-start;
  // gap: 16px;
}
</style>
