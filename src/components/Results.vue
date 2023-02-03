<template>
  <p>Reaction Time: {{ score }} ms</p>
  <div class="rank">
    {{ rank }}
  </div>
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
      this.rank = "Master";
    } else if (this.score < 400) {
      this.rank = "Expert";
    } else if (this.score < 700) {
      this.rank = "Average";
    } else if (this.score < 1000) {
      this.rank = "Beginner";
    } else {
      this.rank = "Newbie";
    }
  },
};
</script>

<style>
.rank {
  font-size: 1.4em;
  color: #0faf87;
  font-weight: bold;
}
</style>
