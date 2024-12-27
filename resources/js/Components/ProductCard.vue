<script setup lang="ts">
defineProps<{
  image: string
  title: string
  price: number
  seller?: string
}>()
</script>

<template>
  <div class="bg-white rounded-lg shadow-sm hover:shadow-md transition-shadow duration-200 cursor-pointer">
    <div class="aspect-square overflow-hidden rounded-t-lg">
      <img :src="image" :alt="title" class="w-full h-full object-cover" />
    </div>
    <div class="p-3">
      <h3 class="text-sm text-gray-800 line-clamp-2">{{ title }}</h3>
      <p class="text-lg font-bold text-gray-900 mt-1">¥{{ price.toLocaleString() }}</p>
      <p v-if="seller" class="text-xs text-gray-500 mt-1">{{ seller }}</p>
    </div>
  </div>
</template>