<script setup>
import { ref } from 'vue'
const isActive = ref(false)
const display = () => {
  isActive.value = !isActive.value
}
</script>

<template>
  <div>
    <h1 v-show="isActive">Displayed V-Show</h1>
    <h1 v-if="isActive">Displayed V-If</h1>
    <h1 v-else>Displayed V-Else</h1>
    <button @click="display">Active</button>
  </div>
</template>

<style></style>
