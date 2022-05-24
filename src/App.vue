<template>
  <h1 class="title">{{ title }}</h1>
  <p>Welcome...</p>
  <div v-if="showModal">
    <Modal :header="header" :text="text" theme="sale" @close="toggleModal">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Ninja Givaway!</h1>
      <p>Grab your ninja swag for half price!</p>
    </Modal>
  </div>
  <div v-if="showModal2">
    <Modal2 :header="header" :text="text" theme="dark" @close="toggleModal2">
      <template v-slot:links>
        <a href="#">sign up now</a>
        <a href="#">more info</a>
      </template>
      <h1>Master Givaway!</h1>
      <p>Grab your master swag for quarter price!</p>
    </Modal2>
  </div>
  <button @click="toggleModal">Open Modal</button>
  <button @click="toggleModal2">Open Modal2</button>
</template>

<script>
import Modal from "./components/Modal.vue";
import Modal2 from "./components/Modal2.vue";

export default {
  name: "App",
  components: {
    Modal,
    Modal2,
  },
  data() {
    return {
      title: "My First Vue App 🔥🔥🔥",
      header: "Sign up for the Giveaway!",
      text: "Grab your ninja swag for half price!",
      showModal: false,
      showModal2: false,
    };
  },
  methods: {
    toggleModal() {
      this.showModal = !this.showModal;
    },
    toggleModal2() {
      this.showModal2 = !this.showModal2;
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
.title {
  border-bottom: 1px solid #ddd;
  display: inline-block;
  padding-bottom: 10px;
}
</style>
