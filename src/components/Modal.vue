<template>
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      {{ header }}
      <h1>Modal</h1>
      <p>modal content</p>
      <p>{{ text }}</p>
    </div>
  </div>

  <!-- MODAL 2 slot -->
  <div class="backdrop" @click.self="closeModal">
    <div class="modal" :class="{ dark: theme === 'dark' }">
      <slot></slot>
    </div>
  </div>
</template>

<script>
export default {
  props: ["header", "text", "theme"],
  methods: {
    closeModal() {
      this.$emit("close");
    },
  },
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