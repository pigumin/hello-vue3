<template>
  <div>
    <h1>Hello组件</h1>
    <p>由provide接收到的消息是 "{{ messageRef }}"</p>
    <button @click="updateMessageRef">点我</button>
  </div>
</template>

<script>
  import { inject } from "vue";
  export default {
    setup() {
      const messageRef = inject('messageRef');
      const updateMessageRef = () => {
        messageRef.value = "依赖注入学习";
      }
      return {
        messageRef,
        updateMessageRef
      };
    },
  };
</script>
