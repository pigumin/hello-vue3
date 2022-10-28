<template>
  <div>
    <header>
      <slot name="header" :countRef="countRef"></slot>
    </header>
    <main>
      <slot :flagRef="flagRef"></slot>
    </main>
    <footer>
      <slot name="footer" :titleRef="titleRef"></slot>
    </footer>
  </div>
</template>

<script>
  import { ref } from "vue";
  export default {
    setup() {
      const countRef = ref(100);
      const titleRef = ref("标题");
      const flagRef = ref(true);
      return {
        countRef,
        titleRef,
        flagRef,
      };
    },
  };
</script>
