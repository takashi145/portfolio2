<script setup lang="ts">
interface Product {
  image: string | null;
  name: string;
  description: string | null;
  url: string | null;
}

defineProps({
  product: {
    type: Object as () => Product,
    required: true
  }
})
</script>
<template>
  <div class="relative">
    <img 
      :src="product.image ? product.image : '//placehold.jp/a9a9a9/ffffff/300x200.png?text=No Image' " 
      class="block h-auto sm:h-52 lg:h-64 w-full shadow-lg max-w-full bg-gray-300 rounded-lg transition hover:scale-110 delay-150 dark:bg-slate-700 border border-gray-300 dark:border-gray-600" 
      :alt="product.name" 
    />
    <a :href="product.url ? product.url : '#'" class="absolute inset-0 cursor-pointer bg-black bg-opacity-70 flex flex-col items-center justify-center rounded-lg hover:ring-4 opacity-0 hover:opacity-100 transition-transform duration-500 ease-in-out">
      <h2 class="text-white text-center text-2xl font-semibold mb-3">{{ product.name }}</h2>
      <p class="text-white text-center text-sm">{{ product.description }}</p>
    </a>
  </div>
</template>
