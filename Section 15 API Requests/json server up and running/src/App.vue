<template>
  <div>Hello, World!</div>
  <p v-if="error" class="error">{{ error }}</p>
  <div v-for="place in state.destinations" :key="place.id">
    <p>{{ place.name }} — {{ place.days }} days — ${{ place.price }}</p>
    <p>{{ place.funFact }}</p>
  </div>
</template>
<script setup>
import { reactive, onMounted } from 'vue'

const API = 'http://localhost:3000/destination'

const state = reactive({
  destinations: [],
  error: null,
})

onMounted(async () => {
  try {
    const response = await fetch(API)
    if (!response.ok) {
      throw new Error(`HTTP ${response.status}`)
    }
    state.destinations = await response.json()
  } catch (e) {
    state.error =
      e instanceof Error
        ? e.message
        : 'Failed to load destinations. Is json-server running? (npm run server)'
  }
})
</script>
<style scoped>
.error {
  color: #c00;
}
</style>
