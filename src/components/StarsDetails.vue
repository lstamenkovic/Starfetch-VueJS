<script>
import starData from "../assets/stars.json";
export default {
  name: "StarDetails",
  props: {
    starIndex: Number,
  },
  data() {
    return {
      zvezde: starData,
      x: this.starIndex,
    };
  },
};
</script>
<template>
  <p>
    <span class="coloredAttr">{{ this.zvezde[this.starIndex].name }}</span>
    <br />
    <br />
    <span class="coloredAttr">Quadrant</span>&#58;&nbsp;<span>{{ this.zvezde[this.starIndex].quadrant }}</span>
    <br />
    <span class="coloredAttr">Right ascension</span>&#58;&nbsp;<span>{{
      this.zvezde[this.starIndex].right_ascension
    }}</span>
    <br />
    <span class="coloredAttr">Declination</span>&#58;&nbsp;<span>{{
      this.zvezde[this.starIndex].declination
    }}</span>
    <br />
    <span class="coloredAttr">Area</span>&#58;&nbsp;<span>{{ this.zvezde[this.starIndex].area }}</span>
    <br />
    <span class="coloredAttr">Main stars</span>&#58;&nbsp;<span>{{ this.zvezde[this.starIndex].main_stars }}</span>
  </p>
</template>

<style scoped>
p {
  text-align: left;
}
.coloredAttr {
  font-weight: bold;
  color: #8be9fd;
}
</style>
