<template>
  <div>
    <input ref="inputRef" />
  </div>
</template>

<script>
  import { ref, onMounted } from "vue";
  export default {
    setup() {
      const inputRef = ref(null);
      onMounted(() => {
        console.log(inputRef);
        inputRef.value.focus();
      });
      return {
        inputRef,
      };
    },
  };
</script>
