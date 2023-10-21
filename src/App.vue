<template>
  <div>
    <h1>Reaction Timer</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame" />
   
    <Results v-if='showResult' :score="score" />
    <Child @child-event="handleChildData" />
    <p>Data received from child component: {{ childData }}</p>
  </div>
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";
import Child from "./components/Child.vue";
export default {
  name: "App",
  components: { Block, Results, Child },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      childData: "",
      showResult: false,
    };
  },
  methods: {
    start() {
      this.isPlaying = true;
      this.delay = 1000 + Math.random() * 5000;
      console.log(this.delay);
      this.showResult = false;
    },
    mounted() {
      console.log("mounted app");
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      console.log("endGme", this.score);
      this.isPlaying = false;
      this.showResult = true;
    },
    handleChildData(data) {
      this.childData = data;
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
  color: #172838;
  margin-top: 60px;
}
.active {
  background-color: rgb(255, 127, 238);
}
</style>
