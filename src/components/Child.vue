<template>
  <button @click="sendDataToParent">Send Data to Parent</button>
</template>

<script>
export default {
  methods: {
    sendDataToParent() {
      const data = "Hello from child component!";
      this.$emit("child-event", data);
    },
  },
};
</script>

<style></style>
