<template>
  <div>
    <h1>Hello组件</h1>
    <p>由provide接收到的消息是 "{{message}}"</p>
  </div>
</template>

<script>
  import { inject } from "vue";
  export default {
    setup() {
      const message = inject('message');
      return {
        message
      };
    },
  };
</script>
