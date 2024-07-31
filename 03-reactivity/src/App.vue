<script setup>
import { nextTick, ref } from 'vue'

// export default {
//   setup() {
//     const count = ref('Komachi') => { value: "Komachi" }
//     return {
//       count
//     }
//   }
// }

const count = ref(0)
const increase = () => {
  // Tương tác với ref trong script phải tương tác qua value, trên template thì không cần
  count.value++
}

// Nếu dùng const object = reactive({}) thì không cần phải .value  mà là object.count,... luôn
const object = ref({
  count: 2,
  user: {
    age: 18
  },
  array: [1, 2, 3]
})

const change = () => {
  object.value.count++
}
const increaseNextTick = async () => {
  count.value++
  console.log(document.getElementById('count').innerText)
  await nextTick()
  console.log(document.getElementById('count').innerText)
}
</script>

<template>
  <div>
    <p>{{ count }}</p>
    <p>{{ object.count }}</p>
    <p id="count">Next Tick{{ count }}</p>
    <button @click="increase">Increase</button>
    <button @click="change">Change Object</button>
    <button @click="increaseNextTick">Increase Next Tick</button>
  </div>
</template>

<style scoped></style>