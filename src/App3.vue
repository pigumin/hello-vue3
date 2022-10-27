<template>
  <Hello :level="3" title="标题" ref="helloRef" />
</template>

<script>
  import { ref, onMounted } from "vue";
  import Hello from "./components/Hello.vue";
  export default {
    components: {
      Hello,
    },
    setup() {
      const helloRef = ref(null);
      onMounted(() => {
        const { value } = helloRef;
        console.log(value.level);
        console.log(value.title);
        console.log(value.count);
        value.hello();
        value.world();
      });
      return {
        helloRef,
      };
    },
  };
</script>
