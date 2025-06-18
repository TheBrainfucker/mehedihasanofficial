<template>
  <article>
    <time
      class="relative z-10 order-first mb-2 flex items-center text-sm text-gray-400 dark:text-gray-500 pl-3.5"
      datetime="2022-09-05"
      ><span
        class="absolute inset-y-0 left-0 flex items-center"
        aria-hidden="true"
        ><span
          class="h-4 w-0.5 rounded-full bg-gray-200 dark:bg-gray-500"
        ></span
      ></span>
      {{ getReadableDate(news.published) }}
    </time>
    <!-- <h2
      class="text-base font-semibold font-display tracking-tight text-gray-800 dark:text-gray-100 group-hover:text-lightaccent dark:group-hover:text-darkaccent"
    >
      {{ news.title }}
    </h2> -->
    <p v-html="news.description" class="relative z-10 mt-1 text-sm text-gray-600 dark:text-gray-300">
      
    </p>
  </article>
</template>

<script setup>
defineProps({
  news: {
    type: Object,
    required: true,
  },
});

const getReadableDate = (dateString) => {
  const date = new Date(dateString);
  return date.toLocaleDateString("en-US", {
    year: "numeric",
    month: "short",
    day: "numeric",
  });
};
</script>