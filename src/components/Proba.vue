<script>
export default {
  props: {
    title: Number,
  },
};
</script>
<template>
  <h2>{{ title }}</h2>
</template>
<style scoped>
  h2 {
    font-size: 2rem;
    color: plum;
  }
</style>
