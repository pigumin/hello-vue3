<template>
  <div>
    <header>
      <slot name="header"></slot>
    </header>
    <main>
      <slot></slot>
    </main>
    <footer>
      <slot name="footer"></slot>
    </footer>
  </div>
</template>

<script>
  export default {
    setup(props, { slots }) {
      console.log(slots);
      if (slots.header) {
        console.log(slots.header());
      }
      if (slots.default) {
        console.log(slots.default());
      }
      if (slots.footer) {
        console.log(slots.footer());
      }
    },
  };
</script>
