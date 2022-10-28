<template>
  <div>
    <Hello>
      <template v-slot:header> Header </template>
      <template v-slot:default> Body </template>
      <template v-slot:footer> Footer </template>
    </Hello>
  </div>
</template>

<script>
  import Hello from "./components/Hello2.vue";
  export default {
    components: {
      Hello,
    },
  };
</script>
