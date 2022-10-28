<template>
  <div>
    <h1>App组件</h1>
    <p>modelValueRef：{{ modelValueRef }}</p>
    <hr />
    <Hello v-model="modelValueRef" />
  </div>
</template>

<script>
  import { ref } from "vue";
  import Hello from "./components/Hello3.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
      const modelValueRef = ref("今天")
      return {
        modelValueRef,
      };
    },
  };
</script>
