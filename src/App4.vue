<template>
  <div>
    <h1>App组件</h1>
    <p>title：{{ titleRef }}</p>
    <p>count：{{ countRef }}</p>
    <hr />
    <Hello v-model:title="titleRef" v-model:count="countRef"/>
  </div>
</template>

<script>
  import { ref } from "vue";
  import Hello from "./components/Hello4.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
      const titleRef = ref("今天")
      const countRef = ref(10)
      return {
        titleRef,
        countRef
      };
    },
  };
</script>
