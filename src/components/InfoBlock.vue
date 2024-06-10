<script setup>
defineProps({
  title: String,
  description: String,
  imgUrl: String
})
</script>

<template>
  <div class="mx-auto flex w-72 flex-col items-center text-center">
    <img height="80" width="80" :src="imgUrl" alt="Info image" />
    <h2 class="mt-4 text-2xl font-medium">{{ title }}</h2>
    <p class="mt-2 text-gray-400">{{ description }}</p>
  </div>
</template>
