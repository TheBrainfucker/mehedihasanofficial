<template>
  <main class="min-h-screen">
    <AppHeader class="mb-16" title="News and Highlights" />
    <ul v-if="newsItems" class="space-y-8">
      <li v-for="(news, id) in newsItems" :key="id">
        <AppNewsCard :news="news" />
      </li>
    </ul>
  </main>
</template>

<script setup>
import newsData from '@/data/news';

const newsItems = ref(newsData);

const description =
  "All of my long-form thoughts on programming, user interfaces, product design, and more, collected in chronological order.";
useSeoMeta({
  title: "News | MehediHasanOfficial",
  description,
});

// const { data: newsItems } = await useAsyncData("all-articles", () =>
//   queryContent("/news").sort({ published: -1 }).find()
// );
</script>
