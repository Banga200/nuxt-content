<script setup>
const { data: page } = await useAsyncData('landing', () =>
  queryContent('/landing').findOne()
)
</script>

<template>
  <section class="flex flex-col items-center justify-center text-center p-10">
    <img v-if="page?.heroImage" :src="page?.heroImage" alt="Hero" class="w-1/2 mb-6" />
    <h1 class="text-4xl font-bold mb-4">{{ page?.title }}</h1>
    <p class="text-lg mb-6">{{ page?.description }}</p>
    <button class="bg-green-600 text-white px-6 py-3 rounded-lg">
      {{ page?.cta }}
    </button>
  </section>
</template>
