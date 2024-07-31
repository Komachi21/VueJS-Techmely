<script setup>
import { ref } from 'vue'
const text = ref('Hello World')
const handleInputValue = (e) => {
  text.value = e.target.value
}

const checkedNames = ref([])
const radioChecked = ref()
const selected = ref([])
const first = ref('first') // binding :value
</script>

<template>
  <div>
    <h1>Form Input Binding</h1>
    <p>{{ text }} {{ typeof(text) }}</p>
    <form action="">
      <input type="text" :value="text" @input="handleInputValue" />
      <input type="text" v-model.lazy="text" />
      <input type="text" v-model.number="text" />

      <p>Checkbox: {{ checkedNames }}</p>
      <input type="checkbox" id="a" v-model="checkedNames" value="A" />
      <label for="a">A</label>
      <input type="checkbox" id="b" v-model="checkedNames" value="B" />
      <label for="b">B</label>

      <p>Radio: {{ radioChecked }}</p>
      <input type="radio" v-model="radioChecked" :value="first" />
      <input type="radio" v-model="radioChecked" value="B" />

      <p>Select: {{ selected }}</p>
      <select name="" id="" v-model="selected" multiple>
        <option value="{name: 'A'}" checked>A</option>
        <option value="B">B</option>
        <option value="C">C</option>
      </select>
    </form>
  </div>
</template>

<style></style>
