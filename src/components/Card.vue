<script setup>
defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number,
  isFavorite: Boolean,
  isAdded: Boolean,
  onClickAdd: Function,
  onClickFavorite: Function
})
</script>

<template>
  <div
    class="relative h-[357px] cursor-pointer rounded-3xl border border-slate-100 bg-white p-8 transition hover:-translate-y-2 hover:shadow-xl"
  >
    <img
      v-if="onClickFavorite"
      :src="!isFavorite ? '/like-1.svg' : '/like-2.svg'"
      alt="Like 1"
      class="absolute left-8 top-8"
      @click="onClickFavorite"
    />

    <img :src="imageUrl" alt="Sneaker" class="mx-auto h-[140px]" />

    <p class="mt-2 line-clamp-2 h-[48px]">{{ title }}</p>

    <div class="mt-10 flex items-end justify-between">
      <div class="flex flex-col">
        <span class="text-slate-400">Цена:</span>
        <b>{{ price }} руб.</b>
      </div>

      <img
        v-if="onClickAdd"
        @click="onClickAdd"
        :src="!isAdded ? '/plus.svg' : '/checked.svg'"
        alt="Plus"
        class="h-fit"
      />
    </div>
  </div>
</template>
