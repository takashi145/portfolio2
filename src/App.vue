<script setup lang="ts">
import ToggleDarkMode from './components/ToggleDarkMode.vue';
import ProductCard from './components/ProductCard.vue';
import ScrollToTopButton from './components/ScrollToTopButton.vue';
import products from './data/products.json';

</script>
<template>
  <div class="min-h-screen bg-gray-100 dark:bg-slate-800 selection:text-blue-500 dark:selection:text-green-400">
    <SplashScreen />

    <div class="max-w-7xl mx-auto pb-8">
      <!-- Dark Mode Toggle component -->
      <div class="text-end px-3 pt-3">
        <ToggleDarkMode />
      </div>

      <!-- ポートフォリオのヘッダー -->
      <div class="mb-6 pb-6 border-b border-gray-600 mx-auto max-w-screen-xl text-center">
        <h1 class="mb-8 text-4xl sm:text-5xl font-extrabold tracking-tight leading-none text-gray-900 lg:text-6xl dark:text-white">Welcome to my portfolio</h1>

        <div class="mb-5 flex justify-center">
          <img src="https://avatars.githubusercontent.com/u/84027833?s=400&u=2a47f99db63cdd16478f99daa60b84978ab44c85&v=4" alt="profile" class="rounded-full h-32 w-32 ring-4">
        </div>

        <p class="mb-3 font-normal text-gray-800 lg:text-lg sm:px-16 lg:px-48 dark:text-gray-400">
          高橋周平
        </p>

        <p class="mb-3 font-normal text-gray-800 lg:text-lg sm:px-16 lg:px-48 dark:text-gray-400">
          まだまだですが、頑張ります。
        </p>

        <a href="https://github.com/takashi145" target="_blank" rel="noopener noreferrer" class="text-white bg-[#24292F] hover:bg-[#24292F]/90 focus:ring-4 focus:outline-none focus:ring-[#24292F]/50 font-medium rounded-lg text-sm px-5 py-2.5 text-center inline-flex items-center border dark:border-gray-600 dark:focus:ring-gray-500 dark:hover:bg-[#050708]/30 mb-3">
          <svg class="w-6 h-6" aria-hidden="true" focusable="false" data-prefix="fab" data-icon="github" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 496 512"><path fill="currentColor" d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3 .3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5 .3-6.2 2.3zm44.2-1.7c-2.9 .7-4.9 2.6-4.6 4.9 .3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3 .7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3 .3 2.9 2.3 3.9 1.6 1 3.6 .7 4.3-.7 .7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3 .7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3 .7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"></path></svg>
          <span class=""></span>
        </a>
      </div>

      <!-- コンテンツエリア -->
      <div class="space-y-14">
        <!-- 公開している制作物一覧 -->
        <div id="product" class="min-h-screen lg:mx-24 px-6 sm:px-12 pt-3 pb-12">
          <h2 class="flex underline items-center justify-center text-2xl font-semibold text-gray-800 mb-5 dark:text-white">
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 mr-2">
              <path stroke-linecap="round" stroke-linejoin="round" d="M9 17.25v1.007a3 3 0 01-.879 2.122L7.5 21h9l-.621-.621A3 3 0 0115 18.257V17.25m6-12V15a2.25 2.25 0 01-2.25 2.25H5.25A2.25 2.25 0 013 15V5.25m18 0A2.25 2.25 0 0018.75 3H5.25A2.25 2.25 0 003 5.25m18 0V12a2.25 2.25 0 01-2.25 2.25H5.25A2.25 2.25 0 013 12V5.25" />
            </svg>
            制作物
          </h2>

          <div class="grid grid-cols-1 md:grid-cols-2 gap-8 lg:gap-12">
            <ProductCard 
              v-for="product in products" 
              :key="product.id" 
              :product="product"
            />
          </div>
        </div>
      </div>
    </div>

    <!-- ScrollToTopButton component -->
    <ScrollToTopButton />
  </div>
</template>

