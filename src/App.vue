<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <div v-if="showModal">
    <Modal :theme="success" @close="toggleModal">
      <template v-slot:links>
        <a href="#">Soy un link</a>
        <a href="#">Soy otro link</a>
      </template>
      <h1>Success</h1>
      <p>Soy un modal con la clase success</p>
    </Modal>
  </div>
  <div v-if="showModalTwo">
    <Modal :theme="warning" @close="toggleModalTwo">
      <template v-slot>
        <h1>WARNING</h1>
        <p>Soy un modal con la clase warning</p>
      </template>
    </Modal>
  </div>
  <button @click="toggleModal">Open modal</button>
  <button @click="toggleModalTwo">Open Modal II</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "HandyMarian",
      theme: "",
      showModal: false,
      showModalTwo: false,
    };
  },
  methods: {
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
h1 {
  border-bottom: 1px solid #2c3e50;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
