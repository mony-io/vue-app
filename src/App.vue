<template>
  <h1>Mony, Reaction Timer</h1>
  <button @click="start">Play</button>
  <Block v-if="isPlaying" :delay="delay" @end="endGame" />
  <Results v-if="showResults" :score="score" />
</template>

<script>
import Block from "./components/Block.vue";
import Results from "./components/Results.vue";

export default {
  name: "App",
  components: { Block, Results },
  data() {
    return {
      isPlaying: false,
      delay: null,
      score: null,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.score = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
    },
  },
};
</script>

<style>
#app {
  font-family: sans-serif;
  text-align: center;
  color: #444;
  margin-top: 60px;
}
button {
  background: #ddd;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  font-size: 1.4rem;
  letter-spacing: 1px;
  cursor: pointer;
  margin: 10px;
}
button:hover {
  background: #bbb;
}
button[disabled] {
  opacity: 0.2;
  cursor: not-allowed;
}
</style>
