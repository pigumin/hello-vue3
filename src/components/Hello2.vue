<template>
  <div>
    Hello组件
    <hr />
    <p>name：{{ name }}</p>
    <p>age：{{ age }}</p>
  </div>
</template>

<script>
  export default {
    props: {
      name: {
        type: String,
        default: "张三",
      },
      age: {
        type: Number,
        default: 30,
      },
    },
    setup(props) {
      console.log(props.name);
      console.log(props.age);
    },
  };
</script>
