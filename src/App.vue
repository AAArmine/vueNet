<template>
  <div class="backdrop">
    <h1>my first {{ title }}</h1>
    <div class="modal">
      <h1>Modal title</h1>
      <p>modal text</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      title: "VUE",
    };
  },
  components: {},
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
