<template>
  <p>Reaction Time: {{ score }} ms</p>
  <p class="ranks">{{ rank }}</p>
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
      this.rank='Hero fingers!'
    }
    else if(this.score<400){
      this.rank='Rapid!!!!'
    }
    else{
    this.rank='snail pace :('
    }
  },
};
</script>

<style>
.ranks{
font-size: 1.4em;
color:aqua;
font-weight: bold;
}






</style>
