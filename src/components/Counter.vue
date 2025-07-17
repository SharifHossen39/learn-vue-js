<script setup lang="ts">
import { computed, reactive } from 'vue'

const author = reactive({
  name: 'John Doe',
  books: ['Vue 2 - Advanced Guide', 'Vue 3 - Basic Guide', 'Vue 4 - The Mystery'],
})
const isPublishedBooks = computed(() => {
  return author.books.length > 0 ? 'Yes, He published books' : 'No, He did not published books'
})

function isPublishBooks2() {
  return author.books.length > 0 ? 'Yes, He published books' : 'No, He did not published books'
}

function makeBooksListEmpty() {
  author.books = [];
}
</script>

<template>
  <p>Author Name: {{ author.name }}</p>
  <p>{{ isPublishedBooks }}</p>
  <p>{{ isPublishBooks2() }}</p>
  <button @click="makeBooksListEmpty">action</button>
</template>

<style scoped>
button {
  font-weight: bold;
}
</style>
