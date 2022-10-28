<template>
  <div>
    <h1>App组件</h1>
    <hr />
    <Hello @eventNoParam="eventNoParam" @eventWithParam="eventWithParam" />
  </div>
</template>

<script>
  import Hello from "./components/Hello2.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
      const eventNoParam = () => {
        console.log("eventNoParam函数被触发了...");
      }
      const eventWithParam = (param1, param2) => {
        console.log(`eventWithParam函数被触发了...参数是：${param1}, ${param2}`);
      }
      return {
        eventNoParam,
        eventWithParam
      }
    }
  };
</script>
