<script setup>
import { ref, reactive } from 'vue'
const items = ref([
  { message: 'Foo', id: 1 },
  { message: 'Bar', id: 2 }
])
const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
})
/**
 * Không khuyến khích việc sử dụng v-if và v-for trên cùng một phần tử do quy định ưu tiên ngầm
 * Nếu muốn kết hợp v-for và v-if thì nên bọc lại 
 * <template v-for="todo in todos">
      <li v-if="!todo.isComplete">
        {{ todo.name }}
      </li>
  </template>
 */

/**
 * - Key nên là các giá trị duy nhất, thường do BE trả ra
 * - Không nên sử dụng chỉ số của mảng
 * - Không thay đổi key, không nên phụ thuộc vào dữ liệu có thể thay đổi
 */

// keyup.enter
</script>

<template>
  <div>
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.message }}</li>
    </ul>
    <span v-for="n in 10" :key="n"> {{ n + ' ' }}</span>
    <h2>V-for Object</h2>
    <li v-for="(value, key, index) in myObject" :key="key">
      ({{ value }} : {{ key }} : {{ index }})
    </li>
  </div>
</template>

<style></style>
