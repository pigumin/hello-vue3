<template>
  <div>
    <p>{{ msg }}</p>
    <button @click="clickMe">点我</button>
  </div>
</template>


<script>
  import { ref, watch } from "vue";
  export default {
    setup() {
      const msg = ref("hello vue3")
      const clickMe = () => {
        msg.value = msg.value === "hello vue3" ? "vue3 hello" : "hello vue3"
      }
      watch(msg, (newMsg) => {
        console.log(`msg is ${newMsg}`);
      })
      return {
        msg,
        clickMe
      }
    },
  };
</script>

