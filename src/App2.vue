<template></template>
<script>
  import { reactive } from "vue";
  export default {
    setup() {
      const person = { name: "zhangsan", age: 18 };
      const personPoxy = reactive(person);
      console.log(person === personPoxy);         // false

      const personPoxy2 = reactive(person);
      console.log(personPoxy === personPoxy2);    // true

      const personPoxy3 = reactive(personPoxy);
      console.log(personPoxy === personPoxy3);    // true
    },
  };
</script>
