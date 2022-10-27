<template>
  <h1>Hello</h1>
</template>

<script>
  import { ref } from "vue";
  export default {
    props: {
      title: {
        type: String,
        default: ""
      },
      level: {
        type: Number,
        default: 0
      },
    },
    setup() {
      const count = ref(0);
      const hello = () => {
        console.log("hello...");
      };
      const world = () => {
        console.log("world...");
      };
      return {
        count,
        hello,
        world
      }
    },
  };
</script>
