<template>
  <h1>{{ title }}</h1>
  <div v-if="showModal">
    <Modal :title="modalTitle" :description="description" @close="toggleModal">
      <ul class="ul">
        <li class="list">Payment Method: 1</li>
        <li class="list">Payment Method: 2</li>
        <li class="list">Payment Method: 3</li>
      </ul>
      <template v-slot:links>
        <div class="btn__container">
          <a href="#" class="btn">Payment Now</a>
          <a href="#" class="btn">More Info</a>
        </div>
      </template>
    </Modal>
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
.ul {
  list-style: none;
  margin: 0;
  margin-left: 10px;
  padding: 20px;
  text-align: left;
  background: #fcdcdc;
  border-radius: 10px;
}
.list {
  line-height: 2rem;
}
.btn__container {
  width: 100%;
  margin: 10px 0;
  padding: 0;
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.btn {
  border: 2px solid coral;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
}
</style>
