<template>
  <h1>{{ title }}</h1>
  <p>Welcome</p>
  <div v-if="showmod">
    <Modal theme="sale" @close="togglemod">
      <template v-slot:links>
        <a href="#">Learn more</a>
        <a href="#">About Us</a>
      </template>
      <h1>Here is Web</h1>
      <p>Get the Chance NOW!</p>
    </Modal>
  </div>
  <button @click="togglemod">Open Modal</button>
</template>

<script>
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "LOL!",
      showmod: false,
    };
  },

  methods: {
    togglemod() {
      this.showmod = !this.showmod;
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
