<template>
  <h1 id="dom">{{ count }}</h1>
  <button @click="clickMe">点我</button>
</template>
<script>
  import { ref, watch } from "vue";
  export default {
    setup() {
      const count = ref(0);
      const clickMe = () => {
        count.value++;
      };
      watch(count, () => {
        console.log("在dom更新前触发的watch回调函数");
        const dom = document.querySelector("#dom");
        console.log(dom.innerHTML);
      });
      watch(
        count,
        () => {
          console.log("在dom更新后触发的watch回调函数");
          const dom = document.querySelector("#dom");
          console.log(dom.innerHTML);
        },
        {
            flush: 'post'
        }
      );
      return {
        count,
        clickMe,
      };
    },
  };
</script>
