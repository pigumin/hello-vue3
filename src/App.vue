<template>
  <h1>msg：{{ msg }}</h1>
  <div style="margin-bottom: 10px">
    <button @click="clickMe">更新msg</button>
  </div>
  <div>
    <button @click="noHello">卸载Hello组件</button>
  </div>
  <Hello v-if="flag"/>
</template>

<script>
  import { onBeforeMount, onMounted, onBeforeUpdate, onUpdated, ref } from "vue";
  import Hello from "./components/Hello.vue";
  export default {
    components: {
      Hello
    },
    setup() {
      const flag = ref(true);

      console.log("setup......");
      const msg = ref("Life Cycle")

      onBeforeMount(() => {
        console.log("onBeforeMount......");
      })

      onMounted(() => {
        console.log("onMounted......");
      })

      onBeforeUpdate( ()=> {
        console.log("onBeforeUpdate......");
      })

      onUpdated( ()=> {
        console.log("onUpdated......");
      })

      const clickMe = () => {
        msg.value = "Cycle Life "
      }

      const noHello = () => {
        flag.value = false;
      }

      return {
        msg,
        clickMe,
        flag,
        noHello
      }
    },
  };
</script>

