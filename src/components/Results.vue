<template>
  <div class="results">
    <h2>Results</h2>
    <p>Reaction time: {{ score }} ms</p>
    <p>{{ rank }}</p>
  </div>
</template>

<script>
export default {
  props: ["score"],
  data() {
    return {
      rank: null,
    };
  },
  mounted() {
    if (this.score < 250) {
      this.rank = "Ninja Fingers";
    } else if (this.score < 400) {
      this.rank = "rapid";
    } else {
      this.rank = "snail pace";
    }
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background-color: aquamarine;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
