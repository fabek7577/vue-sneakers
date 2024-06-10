<script setup>
const emit = defineEmits(['onClickRemove'])

defineProps({
  id: Number,
  title: String,
  imageUrl: String,
  price: Number
})
</script>

<template>
  <div class="flex items-center gap-4 rounded-xl border border-slate-200 p-4">
    <img class="h-16 w-16" :src="imageUrl" alt="Sneaker" />

    <div class="flex flex-1 flex-col">
      <p>{{ title }}</p>

      <div class="mt-2 flex justify-between">
        <b class="flex-1">{{ price }} руб.</b>
        <img
          @click="() => emit('onClickRemove')"
          class="cursor-pointer opacity-40 transition hover:opacity-100"
          src="/close.svg"
          alt=""
        />
      </div>
    </div>
  </div>
</template>
