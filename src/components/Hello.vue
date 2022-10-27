<template>
  <h1>Hello组件</h1>
</template>

<script>
  import { onBeforeUnmount, onUnmounted } from "vue";
  export default {
    setup() {
      onBeforeUnmount(() => {
        console.log("onBeforeUnmount......");
      });
      onUnmounted(() => {
        console.log("onUnmounted......");
      });
    },
  };
</script>
