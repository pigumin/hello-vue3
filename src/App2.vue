<template>
  <ul>
    <li ref="itemRefs" v-for="item in list">{{ item }}</li>
  </ul>
</template>

<script>
  import { ref, onMounted } from "vue";
  export default {
    setup() {
      const itemRefs = ref([]);
      const list = ref(['A','B','C'])
      onMounted(() => {
        itemRefs.value.forEach(itemRef => {
            console.log(itemRef);
        })
      });
      return {
        itemRefs,
        list
      };
    },
  };
</script>
