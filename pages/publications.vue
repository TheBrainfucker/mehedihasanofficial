<template>
  <main class="min-h-screen">
    <AppHeader
      class="mb-12"
      title="Publications"
    />
    <div class="space-y-12">
      <ul class="space-y-8">
        <AppUsesHeader title="2025" />
        <AppUsesItem v-for="(item, id) in pub2025" :key="id" :item="item" />
      </ul>
      <ul class="space-y-8">
        <AppUsesHeader title="2023" />
        <AppUsesItem v-for="(item, id) in pub2023" :key="id" :item="item" />
      </ul>
    </div>
  </main>
</template>

<script setup>
import publications2023 from '@/data/publications2023';
import publications2025 from '~/data/publications2025';

const pub2023 = ref(publications2023);
const pub2025 = ref(publications2025);

const description =
  "Software I use, gadgets I love, and other things I recommend. Here’s a big list of all of my favorite stuff.";
useSeoMeta({
  title: "Publications | MehediHasanOfficial",
  description,
});
</script>
