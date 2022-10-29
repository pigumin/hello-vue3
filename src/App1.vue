<template>
  <div>
    <h1>App组件</h1>
    <hr />
    <Hello />
  </div>
</template>

<script>
  import { provide } from "vue";
  import Hello from "./components/Hello1.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
       message = provide("message", "学习依赖注入");
    }
  };
</script>
