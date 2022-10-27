<template>
  <h1>count：{{ count }}</h1>
</template>
<script>
  import { ref, watchEffect } from "vue";
  export default {
    setup() {
      const count = ref(0);
      setInterval(() => {
        count.value++;
      }, 1000);
      watchEffect(() => {
        console.log(
          `触发了watchEffect 当前count的值为${count.value}`
        );
      });
      return {
        count,
      };
    },
  };
</script>
