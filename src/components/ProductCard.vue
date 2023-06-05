<script setup lang="ts">
interface Product {
  image: string | null;
  name: string;
  description: string | null;
  url: string | null;
  skills: string[] | null;
}

defineProps({
  product: {
    type: Object as () => Product,
    required: true
  }
})

</script>
<template>
  <div class="sm:mx-10 md:mx-0">
    <h3 class="text-gray-800 dark:text-white font-semibold mb-1">{{ product.name }}</h3>
    <div class="relative transform transition-all duration-500 hover:scale-105">
      <img 
        :src="product.image ? product.image : '//placehold.jp/a9a9a9/ffffff/300x200.png?text=No Image' " 
        class="block h-auto md:h-64 lg:h-72 w-full shadow-lg max-w-full bg-gray-300 rounded-lg transition hover:scale-110 delay-150 dark:bg-slate-700 border border-gray-300 dark:border-gray-600" 
        :alt="product.name" 
      />
      <a 
        :href="product.url ? product.url : '#'" 
        target="_blank" 
        rel="noopener noreferrer"
        class="absolute inset-0 cursor-pointer bg-black bg-opacity-80 flex flex-col items-center justify-center rounded-lg hover:ring-4 opacity-0 hover:opacity-100 transition-transform duration-500 ease-in-out"
      >
        <h2 class="text-white text-center text-2xl font-semibold mb-3">{{ product.name }}</h2>
        <p class="mb-8 text-white text-center text-sm px-3" style="white-space: pre-wrap;">{{ product.description }}</p>

        <div class="">
          <div 
            v-for="(skill, index) in product.skills" 
            :key="index" 
            class="group relative inline-block bg-gray-200 rounded-full px-3 py-1 sm:text-xs md:text-sm font-semibold text-gray-700 mr-2 mb-2"
          >
            {{ skill }}
          </div>
        </div>
      </a>
    </div>  
  </div>
</template>
