<script setup>
const message = 'Hello World'
const rawHtml = '<span style="color: red">This should be red.</span>'
const buttonId = 'button'
const buttonClass = 'btn'
const isButtonDisable = true
// Binding nhiều thuộc tính
const objectOfAttrs = {
  id: 'container',
  class: 'wrapper'
}
const number = 0
const isDisplay = true
const listString = 'a,b,cac'
const toTitle = (listString) => {
  console.log(listString)
}
const attributeName = "href"
const url = "https://youtube.com"
</script>

<template>
  <div>
    <h1>Syntax</h1>
    <p>
      Message: <b>{{ message }}</b>
    </p>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>
    <button :id="buttonId" :class="buttonClass" :disabled="isButtonDisable">Click here</button>
    <button v-bind="objectOfAttrs">Binding Multiple</button>
    <button @click="toTitle(listString)" v-if="isDisplay">Number: {{ number + 1 }}</button>
    <a v-bind:[attributeName]="url"> Youtube </a>
  </div>
</template>

<style scoped></style>
