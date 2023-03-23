<script>
export default {
  name: 'Header',
  props: {
    title: {
      type: String,
    },
  },
};
</script>

<template>
  <span>{{ title }}</span>
</template>

<style scoped>
span {
  font-size: 3rem;
  color: #ff79c6;
}
</style>
