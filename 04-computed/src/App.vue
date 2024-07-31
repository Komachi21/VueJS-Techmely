<script setup>
import { reactive, computed, ref } from 'vue'

const book = reactive({
  name: 'Book1',
  chapters: []
})

const addChapter = () => {
  book.chapters.push('Chapter')
}

// const isPublished = () => (book.chapters.length > 0 ? 'Có' : 'Không')
const isPublished = computed(() => {
  return book.chapters.length > 0 ? 'Có' : 'Không'
})
/**
 * - Vue nó sẽ theo dõi tất cả dependency tức là các  state phụ thuộc có trong computed
 * để nó tính toán và chỉ cập nhật khi các dependency đó thay đổi => giảm sự tính toán không cần thiết
 * ví dụ trên là chỉ có 1 state, nếu có nhiều state mà state khác thay đổi thì computed nó giúp cho không phải tính toán lại vì lưu trữ trong bộ nhớ
 * nó chỉ tính toán lại khi state nó phụ thuộc thay đổi
 * - Tính phản ứng
 * - Tái sử dụng code
 */

// Ghi đè 1 computed
const firstName = ref('Nguyễn Văn')
const lastName = ref('B')
const fullname = computed({
  get() {
    return firstName.value + ' ' + lastName.value
  },
  set(newValue) {
    [firstName.value, lastName.value] = newValue.split(',')
  }
})

const changeFullName = () => {
  fullname.value = 'Phạm Văn, B'
}
</script>

<template>
  <div>
    <p>bookName: {{ book.name }}</p>
    <p>Đã xuất bản: {{ isPublished }}</p>
    <p>fullname: {{ fullname }}</p>
    <button @click="addChapter">Add Chapter</button>
    <button @click="changeFullName">changeFullName</button>
  </div>
</template>
