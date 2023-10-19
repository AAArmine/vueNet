<template>
  <div>
    <h1>First vue project</h1>
    <p>{{ test }}</p>
    <input type="text" ref="name" />
    <button @click="handleClick">click</button>
    <div v-if="showModal">
      <Modal :theme="theme" @close="handleClick">
        <h2>mod title</h2>
        <p>mod paragraph</p>
        <template v-slot:other><p>some other p</p></template>
      </Modal>
    </div>
  </div>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    Modal,
  },
  data() {
    return {
      test: "value",
      header: "my header",
      textModal: ["paragraph 1", "paragraph 2"],
      theme: true,
      showModal: false,
    };
  },
  methods: {
    handleClick() {
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
.active {
  background-color: rgb(255, 127, 238);
}
</style>
