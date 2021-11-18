<template>
  <div class="slot" :class="{ dark: theme === 'dark' }">
    <slot name="links"></slot>
  </div>
</template>

<script>
export default {
  props: ["dark"],
};
</script>


<style scoped>
.backdrop {
  position: fixed;
  top: 0;
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
}
.modal {
  width: 15rem;
  margin: 1rem auto;
  padding: 1rem;
  border-radius: 10px;
  background: rgb(252, 249, 249);
}
h1 {
  color: rgb(9, 158, 133);
}
.sale {
  color: rgb(250, 250, 250);
  background-color: rgb(138, 49, 223);
}
</style>