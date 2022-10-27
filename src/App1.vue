<template>
  <div>
    <Hello name="李四" :age="40"/>
  </div>
</template>

<script>
  import Hello from "./components/Hello1.vue"
  export default {
    components: {
      Hello
    }
  };
</script>
