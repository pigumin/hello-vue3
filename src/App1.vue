<template>
  <div>
    <Hello>
      <template v-slot:header="headerSlotObj">
        Header {{ headerSlotObj.countRef }}
      </template>
      <template v-slot:default="defaultSlotObj">
        Body {{ defaultSlotObj.flagRef }}
      </template>
      <template v-slot:footer="footerSlotObj">
        Footer {{ footerSlotObj.titleRef }}
      </template>
    </Hello>
  </div>
</template>

<script>
  import Hello from "./components/Hello1.vue";
  export default {
    components: {
      Hello,
    },
  };
</script>
