<template>
  <div class="container">
    <p>{{ countRef }}</p>
    <button @click="addNum">点我</button>
  </div>
</template>
<script>
  import { ref } from "vue";
  export default {
    setup() {
      const countRef = ref(0);
      const addNum = () => {
        countRef.value++;
      }
      return { countRef, addNum };
    },
  };
</script>