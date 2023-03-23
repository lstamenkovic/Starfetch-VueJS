<script>
import starData from '../assets/stars.json'
import Stars from "../components/Stars.vue";
import StarDetails from '../components/StarsDetails.vue'
export default {
  components: {
    Stars,
    StarDetails,
  },
  data() {
    return {
      zvezde: starData,
      z: 17,
      // z: 6,
    }
  },
  methods: {
    starfetch() {
      function RNG(min, max) {
        return Math.floor(Math.random() * (max - min + 1) ) + min;
      }
      let r = RNG(0, this.zvezde.length);
      this.z = r;
      console.log(r);
    },
  },
};
</script>

<template>
    <div class="wrapper">
      <Stars :starIndex="z" id="stars" />
      <StarDetails :starIndex="z" id="starDetails" />
    </div>
    <button @click="starfetch()">Random constellation</button>
</template>

<style scoped>
.wrapper {
  max-width: 800px;
  display: flex;
  flex-direction: column;
  align-items: center;
  margin: 0 auto;
}
#starDetails {
  padding: 20px;
}
</style>
