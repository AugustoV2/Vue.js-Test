<script setup>
import { ref, computed } from 'vue'

import About from './components/TheWelcome.vue'



const routes = {
  
  '/about': About
}

const currentPath = ref(window.location.hash)

window.addEventListener('hashchange', () => {
  currentPath.value = window.location.hash
})

const currentView = computed(() => {
  return routes[currentPath.value ]
})
</script>

<template>
 
  <a href="/about">Aboutaaaa</a> |
 
  <component :is="currentView" />
</template>