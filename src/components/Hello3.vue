<template>
  <div>
    <h1>Hello组件</h1>
    <h3>接收到的 v-model 值是：{{ modelValue }}</h3>
    <button @click="updateModelValue">点我</button>
  </div>
</template>

<script>
  export default {
    props: {
      modelValue: {
        type: String,
        default: "标题",
      },
    },
    emits: ["update:modelValue"],
    setup(props, { emit }) {
      const updateModelValue = () => {
        emit("update:modelValue", "明天");
      };
      return {
        updateModelValue,
      };
    },
  };
</script>
