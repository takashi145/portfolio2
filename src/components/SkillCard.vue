<script setup lang="ts">
import { ref } from 'vue';
import Modal from './Modal.vue';

interface Skill {
  name: string;
  experience: string;
  description: string;
}

const show = ref(false);

defineProps({
  skill: {
    type: Object as () => Skill,
    required: true,
  }
})
</script>
<template>
  <div @click="show = true" class="w-full flex flex-col justify-between p-6 mx-auto bg-white border-2 border-gray-300 rounded-lg shadow-lg dark:bg-gray-800 transform transition-all duration-500 hover:scale-105">
    <div class="text-2xl font-semibold text-gray-700 dark:text-white">
        {{ skill.name }}
    </div>
    <div class="mt-2 text-lg text-gray-600 dark:text-gray-400">
        {{ skill.experience }}
    </div>
  </div>

  <Modal :show="show" @close="show = false">
    <button @click="show = false" class="absolute top-2 right-2">
      <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-5 h-5 text-gray-600 hover:text-gray-800 dark:text-gray-400 dark:hover:text-gray-200">
        <path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
      </svg>
    </button>

    <div class="md:flex">
      <div class="p-6">
        <h2 class="mb-4 uppercase tracking-wide text-xl text-indigo-500 font-semibold">
          Skill: {{ skill.name }}
        </h2>
        <p class="block mt-1 text-md leading-tight font-medium text-black dark:text-gray-200">
          {{ skill.description }}
        </p>
      </div>
    </div>
  </Modal>
</template>
