<template>
  <div class="container">
    <p>{{ stateRef.count }}</p>
    <button @click="addNum">点我</button>
    <button @click="putVal">赋值</button>
  </div>
</template>
<script>
  import { ref } from "vue";
  export default {
    setup() {
      const stateRef = ref({ count: 0 });
      const addNum = () => {
        stateRef.value.count++;
      };
      const putVal = () => {
        stateRef.value = { count: 10 }
      }
      return { stateRef, addNum, putVal };
    },
  };
</script>
