<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <input type="text" ref="name" />
    <button @click="handleClick">ref</button>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Modal header="prpos: header" text="text through props" /> -->
  </div>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal" />
  </div>
  <button @click="toggleModal">open modal</button>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    // HelloWorld
    Modal,
  },
  data() {
    return {
      title: "Vue first app",
      header: "header through props",
      text: "some text through props",
      showModal: false,
    };
  },
  methods: {
    handleClick() {
      console.log(this.$refs.name);
      this.$refs.name.classList.add("active");
      this.$refs.name.focus();
    },
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
