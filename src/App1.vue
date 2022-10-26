<script>
  import { reactive, computed } from "vue";
  export default {
    setup() {
      const author = reactive({
        name: "John Doe",
        books: ["Vue 2 - Advanced Guide", "Vue 3 - Basic Guide", "Vue 4 - The Mystery"],
      });
      // 一个计算属性 ref
      const publishedBooksMessage = computed(() => {
        return author.books.length > 0 ? "Yes" : "No";
      });
      return {
        publishedBooksMessage
      }
    },
  };
</script>

<template>
  <p>Has published books:</p>
  <span>{{ publishedBooksMessage }}</span>
</template>
