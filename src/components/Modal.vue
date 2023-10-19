<template>
  <div class="backdrop" @click.self="closeModal">
    <div :class="{ modal: true, dark: theme }">
      <slot name="other"></slot>
      <slot><span>Default content</span></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: ["theme"],
  data() {
    return {
      title: "VUE",
    };
  },
  methods: {
    closeModal() {
      console.log("close mod");
      this.$emit("close");
    },
  },
  components: {},
};
</script>

<style scoped>
.dark {
  background-color: grey;
}
.backdrop {
  top: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
}
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}
h1 {
  color: aqua;
}
</style>
