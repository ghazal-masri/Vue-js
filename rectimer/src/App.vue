<template>
  <h1>ghazal-timer</h1>
  <button @click="start" :disabled="isplay">Play</button>
  <block v-if="isplay" :delay="delay" @end="endgame" />
  <res v-if="showres" :score="score" />
</template>

<script>
import block from "./components/block.vue";
import res from "./components/res.vue";
export default {
  name: "App",
  components: { block,res },
  data() {
    return {
      isplay: false,
      delay: null,
      score: null,
      showres: false,
    };
  },
  methods: {
    start() {
      this.isplay = true;
      this.delay = 2000 + Math.random() * 5000;
      this.showres = false;
    },
    endgame(reactime) {
      this.score = reactime;
      this.isplay = false;
      this.showres = true;
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
  color: #444;
  margin-top: 60px;
}
</style>
