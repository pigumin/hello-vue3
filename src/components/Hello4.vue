<template>
  <div>
    <h1>Hello组件</h1>
    <h3>接收到的 title 值是：{{ title }}</h3>
    <h3>接收到的 count 值是：{{ count }}</h3>
    <button @click="updateTitle">修改title</button>
    <button @click="updateCount">修改count</button>
  </div>
</template>

<script>
  export default {
    props: {
      title: {
        type: String,
        default: "标题",
      },
      count: {
        type: Number,
        default: 0,
      },
    },
    emits: ["update:title", "update:count"],
    setup(props, { emit }) {
      const updateTitle = () => {
        emit("update:title", "明天");
      };
      const updateCount = () => {
        emit("update:count", 30);
      };
      return {
        updateTitle,
        updateCount,
      };
    },
  };
</script>
