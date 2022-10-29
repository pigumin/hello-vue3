<template>
  <div>
    <h1>App组件</h1>
    <p>我提供的数据是：{{ messageRef }}</p>
    <hr />
    <Hello />
  </div>
</template>

<script>
  import { ref, readonly, provide } from "vue";
  import Hello from "./components/Hello2.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
      const messageRef = ref("学习依赖注入");
      provide("messageRef", readonly(messageRef));
      return {
        messageRef
      }
    }
  };
</script>
