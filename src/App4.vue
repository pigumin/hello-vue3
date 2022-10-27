<template>
  <div>
    <p>x：{{ x }}</p>
    <p>y：{{ y }}</p>
    <button @click="clickMe">点我</button>
  </div>
</template>

<script>
  import { ref, watch } from "vue";
  export default {
    setup() {
      const x = ref(10);
      const y = ref(20);
      watch([x, () => y.value], ([newX, newY]) => {
        console.log(`x is：${newX}, y is：${newY}`);
      });
      const clickMe = () => {
        x.value = 1;
        y.value = 3;
      };
      return {
        x,
        y,
        clickMe,
      };
    },
  };
</script>
