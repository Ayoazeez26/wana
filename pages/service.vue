<template>
  <div class="body">
    <main class="text-primary">
      <AppHeader />
      <!-- <JobDropdown v-if="dataStore.job" /> -->
      <ServiceHero />
      <ServiceSecondSection />
      <ServiceValues />
      <ServiceDiscover />
      <ServiceTrust />
    </main>
    <AppFooter />
  </div>
</template>

<script setup lang="ts">
import { useDataStore } from '@/stores/data'

const dataStore = useDataStore();
</script>

<style scoped></style>
