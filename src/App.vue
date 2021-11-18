<template>
  <div>
    <img alt="Vue logo" src="./assets/logo.png" />
    <h1>{{ title }}</h1>
    <input type="text" ref="name" />
    <button @click="handleClick">ref</button>
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <Modal header="prpos: header" text="text through props" /> -->
  </div>
  <!-- MODAL 1 -->
  <teleport to=".modals" v-if="showModal">
    <Modal :header="header" :text="text" theme="dark" @close="toggleModal" />
  </teleport>
  <!-- MODAL 2 slot" -->
  <teleport to=".modals" v-if="showModalTwo">
    <Modal theme="" @close="toggleModalTwo">
      <h2>slot</h2>
      <p>modal slot</p>
    </Modal>
  </teleport>
  <!-- MODAL BUTTONS -->
  <button @click="toggleModal">open modal</button>
  <button @click="toggleModalTwo">open modal two</button>
  <hr />
  <!-- SLOT -->
  <div>
    <ModalSlot theme="dark">
      <template v-slot:links>
        <h2>slot links</h2>
        <a href="#" class="btn-link">sign up now</a>
        <a href="#" class="btn-link">more info</a>
      </template>
    </ModalSlot>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Modal from "./components/Modal";
import ModalSlot from "./components/ModalSlot";

export default {
  name: "App",
  components: {
    // HelloWorld
    Modal,
    ModalSlot,
  },
  data() {
    return {
      title: "Vue first app",
      header: "header through props",
      text: "some text through props",
      showModal: false,
      showModalTwo: false,
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
    toggleModalTwo() {
      this.showModalTwo = !this.showModalTwo;
    },
  },
};
</script>

<style>
#app,
.modals {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.btn-link {
  margin: 1rem;
}
</style>
