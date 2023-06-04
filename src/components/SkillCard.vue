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
    <div class="md:flex">
      <div class="p-8">
        <h2 class="mb-4 uppercase tracking-wide text-xl text-indigo-500 font-semibold">
          Skill: {{ skill.name }}
        </h2>
        <a href="#" class="block mt-1 text-md leading-tight font-medium text-black hover:underline dark:text-gray-200">
          経験: 約{{ skill.experience }}
        </a>
        <p class="mt-2 dark:text-gray-300">{{ skill.description }}</p>
      </div>
    </div>
  </Modal>
</template>
