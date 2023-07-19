<template>
  <div class="block" v-if="showblock" @click="stopTimer">Click Me!</div>
</template>

<script>
export default {
  props: ["delay"],
  data() {
    return {
      showblock: false,
      timer: null,
      rectime: 0,
    };
  },
  mounted() {
    setTimeout(() => {
      this.showblock = true;
      this.startTimer();
    }, this.delay);
  },
  methods: {
    startTimer() {
      this.timer = setInterval(() => {
        this.rectime += 10;
      }, 10);
    },
    stopTimer() {
      clearInterval(this.timer);
      this.$emit("end", this.rectime);
    },
  },
};
</script>

<style>
.block {
  width: 400px;
  border-radius: 20px;
  background: cadetblue;
  color: white;
  text-align: center;
  padding: 100px 0;
  margin: 40px auto;
}
</style>
