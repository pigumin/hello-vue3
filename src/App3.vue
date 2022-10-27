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
      watch(
        () => x.value + y.value,
        (sum) => {
          console.log(`sum of x + y is：${sum}`);
        }
      );
      const clickMe = () => {
        x.value = 1;
      };
      return {
        x,
        y,
        clickMe,
      };
    },
  };
</script>
