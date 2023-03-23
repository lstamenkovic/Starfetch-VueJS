<script>
import starData from '../assets/stars.json'
import Stars from "../components/Stars.vue";
import StarDetails from '../components/StarsDetails.vue'
export default {
  name: 'StarList',
  components: {
    Stars,
    StarDetails,
  },
  data() {
    return {
      stars: starData,
    }
  },
}
</script>
<template>
  <div class="wrapper">
    <div v-for="(star, index) in stars" class="stars">
      <Stars :starIndex="index"/>
      <StarDetails :starIndex="index"/>
    </div>
  </div>
</template>

<style scoped>
.wrapper {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
div {
  /* margin-left: 300px; */
  display: flex;
  flex-direction: row;
}
</style>
