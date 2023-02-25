<template>
  <p>Reaction time - {{ score }} ms</p>
  <p class="rank">{{ rank }}</p>
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
      this.rank = "Nigga What";
    } else if (this.score < 400) {
      this.rank = "Snail pace...";
    } else if (this.score < 600) {
      this.rank = "Shit Pace...";
    } 
    else {
      this.rank = "GameOver";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4rem;
  color: aquamarine;
  font-weight: bold;
}
</style>
