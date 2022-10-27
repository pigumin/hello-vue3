<template>
  <h1>name：{{ person.name }}</h1>
  <h1>age：{{ person.age }}</h1>
  <h1>area：{{ person.home.area }}</h1>
  <h1>address：{{ person.home.address }}</h1>
  <button @click="changeName">修改姓名</button>
  <button @click="changeAge">修改年龄</button>
  <button @click="changeArea">修改面积</button>
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
      watch(
        () => person.age,
        (newAge) => {
          console.log(`newPerson：${newAge}`);
        }
      );
      watch(
        () => person.home.area,
        (newArea) => {
          console.log(`newArea：${newArea}`);
        }
      );
      const changeName = () => {
        person.name = "李四";
      };
      const changeAge = () => {
        person.age = 20;
      };
      const changeArea = () => {
        person.home.area = 100;
      };
      const changeAddress = () => {
        person.home.address = "上海";
      };
      return {
        person,
        changeName,
        changeAge,
        changeArea,
        changeAddress,
      };
    },
  };
</script>
