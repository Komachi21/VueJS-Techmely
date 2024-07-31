<script setup>
import { ref } from 'vue'
const count = ref(0)
const greet = (event) => {
  console.log(event)
}
const sayHi1 = () => {
  alert('Xin chào 1')
}
const sayHi2 = () => {
  alert('Xin chào 2')
}
/**
  sự kiện click sẽ không lan tỏa nữa
  <a @click.stop="handleEvent"></a>

  sự kiện submit sẽ không làm tải lại trang nữa
  <form @submit.prevent="handleEvent"></form>

  có thể chặn kết hợp các modifier 
  <a @click.stop.prevent="handleEvent"></a>

  chỉ là modifier 
  <form @submit.prevent></form>

  chỉ kích hoạt xử lý nếu sự kiện.target là chính phần tử đó
  tức là không từ một phần tử con -->
  <div @click.self="handleEvent"></div>

  Key Modifiers
 */
</script>

<template>
  <div>
    <h1>Event handling</h1>
    <h1>{{ count }}</h1>
    <button @click="greet">Click</button>
    <button @click="sayHi1">
      Sayhi1
      <button @click.stop="sayHi2">Sayhi2</button>
    </button>
    <input type="text" @keyup.alt.enter="sayHi2" />
  </div>
</template>

<style></style>
