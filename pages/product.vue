<template>
  <div class="bg-white">
    <!-- Header -->
    <header class="border-b border-gray-200 px-4 py-4 flex justify-between items-center">
      <button @click="open = !open" class="text-gray-500 lg:hidden">
        ☰
      </button>
    </header>

    <!-- Product Section -->
    <main class="max-w-4xl mx-auto p-4 lg:flex gap-8">
      <!-- Image Gallery -->
      <div class="lg:w-1/2">
        <img :src="product.images[0].src" :alt="product.name" class="w-full rounded-lg object-cover" />
        <div class="grid grid-cols-4 gap-2 mt-2">
          <img
            v-for="img in product.images"
            :key="img.id"
            :src="img.src"
            :alt="img.alt"
            class="h-16 w-16 object-cover rounded-md cursor-pointer"
            @click="product.images.unshift(product.images.splice(product.images.indexOf(img), 1)[0])"
          />
        </div>
      </div>

      <!-- Product Info -->
      <div class="lg:w-1/2 mt-6 lg:mt-0">
        <h2 class="text-2xl font-bold">{{ product.name }}</h2>
        <p class="text-xl text-indigo-600 mt-2">{{ product.price }}</p>
        <div class="mt-4 text-gray-700" v-html="product.description"></div>
        <button class="mt-6 bg-indigo-600 text-white px-4 py-2 rounded hover:bg-indigo-700">
          Add to Bag
        </button>
      </div>
    </main>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const open = ref(false)

const product = {
  name: 'Minimal Sneaker',
  price: '$99.00',
  description: '<p>This is a premium quality sneaker for everyday use.</p>',
  images: [
    { id: 1, src: 'https://via.placeholder.com/500', alt: 'Sneaker front view' },
    { id: 2, src: 'https://via.placeholder.com/500', alt: 'Sneaker side view' },
    { id: 3, src: 'https://via.placeholder.com/500', alt: 'Sneaker top view' },
    { id: 4, src: 'https://via.placeholder.com/500', alt: 'Sneaker back view' },
  ],
}
</script>

<style>
/* You can keep this empty if Tailwind is configured */
</style>
