<template>
  <div class="backd" @click.self="closemod">
    <div class="modal" :class="{ sale: theme === 'sale' }">
      <slot>Default</slot>
      <div class="actions">
        <slot name="links"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["theme"],
  methods: {
    closemod() {
      this.$emit("close");
    },
  },
};
</script>

<style scoped>
.backd {
  top: 0;
  position: fixed;
  background: rgba(0, 0, 0, 0.5);
  width: 100%;
  height: 100%;
}
.modal {
  width: 400px;
  padding: 20px;
  margin: 100px auto;
  background: white;
  border-radius: 10px;
}

h1 {
  border-radius: 10px;
  color: aquamarine;
}
p {
  font-style: normal;
}
.actions {
  text-align: center;
  margin: 30px 0 10px 0;
}
.actions a {
  color: #333;
  padding: 8px;
  border: 1px solid #eee;
  border-radius: 4px;
  text-decoration: none;
  margin: 10px;
}
.sale {
  background: crimson;
  color: white;
}
.sale h1 {
  color: white;
}
.sale .actions a {
  color: white;
}
</style>
