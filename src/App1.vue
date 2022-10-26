<template>
  <div class="container">
    <p>名字：{{ person.name }}</p>
    <button @click="changeName">改名字</button>
    <p>人数：{{ person.count }}</p>
    <button @click="changeCount">增加人数</button>
    <p>城市：{{ citys }}</p>
    <button @click="addCity">增加城市</button>&nbsp;
    <button @click="removeCity">删除城市</button>&nbsp;
    <button @click="changeCity">修改城市</button>&nbsp;
  </div>
</template>
<script>
  import { reactive } from "vue";
  export default {
    setup() {
      // 定义对象
      const person = reactive({ count: 0, name: "zhangsan" });
      const changeCount = () => {
        person.count++;
      };
      const changeName = () => {
        person.name = person.name === "zhangsan" ? "lisi" : "zhangsan";
      };

      // 定义数组
      const citys = reactive(['北京','上海', '广州', '深圳']);
      const addCity = () => {
        citys.push('重庆');
      }
      const removeCity = () => {
        citys.splice(0, 1);
      }
      const changeCity = () => {
        citys[1] = '西藏';
      }
      return { person, changeCount, changeName, citys, addCity, removeCity, changeCity };
    },
  };
</script>