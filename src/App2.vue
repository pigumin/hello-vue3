<template>
  <div>
    <p>name：{{ person.name }}</p>
    <p>age：{{ person.age }}</p>
    <button @click="clickMe">点我</button>
  </div>
</template>

<script>
  import { reactive, watch } from "vue";
  export default {
    setup() {
      const person = reactive({ name: "张三", age: 30 });
      const clickMe = () => {
        person.name =
          person.name === "张三" ? "李四" : "张三";
        person.age = person.age === 30 ? 20 : 30;
      };
      watch(person, (newPerson) => {
        console.log(
          `person is ${newPerson.name},${newPerson.age}`
        );
      });
      return {
        person,
        clickMe,
      };
    },
  };
</script>
