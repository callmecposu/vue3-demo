<template>
  <h1>Reaction Timer</h1>
  <button @click="start">Play</button>
  <ReactionBlock />
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
    };
  },
  methods: {
    start() {
      this.delay = 2000 + Math.random() * 5000; // delay in MS
      this.isPlaying = true;
      console.log(this.delay);
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
