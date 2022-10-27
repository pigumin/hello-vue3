<template>
  <h1>name：{{ person.name }}</h1>
  <h1>age：{{ person.age }}</h1>
  <h1>area：{{ person.home.area }}</h1>
  <h1>address：{{ person.home.address }}</h1>
  <button @click="changeAge">修改年龄</button>
  <button @click="changeAddress">修改住址</button>
</template>
<script>
  import { reactive, watch } from "vue";
  export default {
    setup() {
      const person = reactive({
        name: "张三",
        age: 30,
        home: { area: 80, address: "北京" },
      });
      watch(person, (newPerson) => {
        console.log(
          `newPerson：${newPerson.name},${newPerson.age},${newPerson.home.area},${newPerson.home.address}`
        );
      });
      const changeAge = () => {
        person.age = 20;
      };
      const changeAddress = () => {
        person.home.address = "上海";
      };
      return {
        person,
        changeAge,
        changeAddress,
      };
    },
  };
</script>
