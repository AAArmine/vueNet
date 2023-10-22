<template>
  <div>
    <h1>form</h1>
    <SignUpForm />
  </div>
</template>

<script>
import SignUpForm from "./components/SignUpForm.vue";
export default {
  name: "App",
  components: { SignUpForm },
  data() {
    return {};
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #172838;
  margin-top: 60px;
}
body {
  margin: 0;
  background: #eee;
}
</style>
