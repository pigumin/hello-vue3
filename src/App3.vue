<template>
  <p>{{ state.count }}</p>
  <div class="handle">
    <button @click="add">点我</button>
    <button @click="putVal1">赋值</button>
    <button @click="putVal2">解构赋值</button>
    <button @click="putVal3">传入一个函数</button>
  </div>
</template>

<script>
  import { reactive } from "vue";
  export default {
    setup() {
      const state = reactive({ count: 0 });
      const add = () => {
        state.count++;
      };
      const putVal1 = () => {
        let n = state.count;
        n = n + 1;
        console.log(n);
      };
      const putVal2 = () => {
        let { count } = state;
        count = count + 1;
        console.log(count);
      };
      const putVal3 = () => {
        callSomeFunction(state.count);
      }

      function callSomeFunction(param) {
        param = param + 1;
        console.log(param);
      }

      return { state, add, putVal1, putVal2, putVal3};
    },
  };
</script>

<style>
    .handle button{
        margin-right: 10px;
    }
</style>
