<template>
  <h1>Reaction Timer</h1>
  <button @click="start" :disabled="isPlaying">Play</button>
  <ReactionBlock v-if="isPlaying" :delay="delay" @end="endGame" />
  <p v-if="showResults">Reaction Time: {{ result }} ms</p>
</template>

<script>
import ReactionBlock from "./components/ReactionBlock.vue";

export default {
  name: "App",
  components: { ReactionBlock },
  data() {
    return {
      isPlaying: false,
      delay: null,
      result: null,
      showResults: false,
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000; // delay in MS
      this.isPlaying = true;
      this.showResults = false;
    },
    endGame(reactionTime) {
      this.result = reactionTime;
      this.isPlaying = false;
      this.showResults = true;
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
</style>
