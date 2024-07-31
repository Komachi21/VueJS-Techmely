<script setup>
import { ref, computed, reactive } from 'vue'
const isActive = ref(true)
const classObject = computed(() => ({
  active: isActive.value && 1 === 2
}))

const classObject2 = reactive({
  active: true,
  'text-danger': true
})

// Binding Style
const colorStyle = ref('red')
// Binding Object
const styleObject = reactive({
  color: 'red',
  fontSize: '20px'
})
// Binding Object with computed
const classObjectComputed = computed(() => ({
  color: 'red',
  fontSize: '20px'
}))
</script>

<template>
  <div>
    // Binding Class
    <button class="button" :class="{ active: isActive }">Active</button>
    <button class="button" :class="classObject">Active</button>
    <button class="button" :class="classObject2">Active</button>
    <button
      class="button"
      :class="['active', isActive ? 'has-error' : '', { 'has-error': isActive }]"
    >
      Binding Class
    </button>

    // Binding Style
    <button class="button" :style="{ color: colorStyle }">Style</button>
    <button class="button" :style="styleObject">styleObject</button>
    <button class="button" :style="classObjectComputed">classObjectComputed</button>
  </div>
</template>

<style>
.button {
  border: none;
  background: #333;
  color: #fff;
  padding: 10px;
  border-radius: 6px;
}
.active {
  border: none;
  background: #000;
  color: #fff;
  padding: 10px;
  border-radius: 6px;
}

.text-danger {
  color: red;
}
</style>
