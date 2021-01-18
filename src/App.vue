<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal
      :title="modalTitle"
      :description="description"
      @close="toggleModal"
    />
  </div>
  <button @click="toggleModal">Show Modal</button>
</template>

<script>
import Modal from "./components/Modal";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "My First View App",
      modalTitle: "Payment Method",
      description: "These are all the payment methods.",
      showModal: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
  },
};
</script>

<style>
html {
  font-size: 100%;
  box-sizing: border-box;
}
*,
*::before,
*::after {
  box-sizing: inherit;
}
body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
