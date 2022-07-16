<script setup lang="ts">
import { ref } from 'vue'

const active = ref(-1)

const btns = ref([
  {
    text: 'Dreamies',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14.828 14.828a4 4 0 01-5.656 0M9 10h.01M15 10h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z" />
</svg>`,
  },
  {
    text: 'Search',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" />
</svg>`,
  },
  {
    text: 'Profile',
    icon: `<svg xmlns="http://www.w3.org/2000/svg" class="h-8 w-8 mx-auto" fill="none" viewBox="0 0 24 24" stroke="currentColor">
  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
</svg>`,
  },
])
</script>

<template>
  <footer class="shadow-lg">
    <div
      class="relative h-20 bg-yellow-100 flex flex-row justify-center items-center"
    >
      <nav class="absolute -top-1/4 sm:-top-2/4">
        <template v-for="(btn, index) in btns" :key="btn.text">
          <button
            :class="
              active === index &&
              'ring-2 ring-yellow-900 ring-opacity-10 shadow-lg text-opacity-100'
            "
            @click="active = index"
            class="shadow-sm rounded-2xl mr-3 p-4 w-16 sm:w-32 bg-gray-50 text-yellow-900 text-xl font-medium text-opacity-50 text-center transition duration-500 ease-out transform hover:-translate-y-3 hover:scale-110"
          >
            <div v-show="btn.icon" v-html="btn.icon" class="mb-2"></div>
            <span
              class="hidden sm:inline-block"
              :class="active === index && 'underline'"
              >{{ btn.text }}</span
            >
          </button>
        </template>
      </nav>
    </div>
  </footer>
</template>

<style scoped>
button {
  text-underline-offset: 0.5rem;
}
</style>
