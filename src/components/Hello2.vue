<template>
  <div>
    <h1>Hello组件</h1>
    <button @click="clickNoParam">触发事件：无参数</button>
    <button @click="clickWithParam('hello')">触发事件：有参数</button>
  </div>
</template>

<script setup>
  const emit = defineEmits(["eventNoParam", "eventWithParam"]);
  const clickNoParam = () => {
    emit("eventNoParam");
  };
  const clickWithParam = (param) => {
    emit("eventWithParam", param, "world");
  };
</script>
