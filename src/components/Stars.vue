<script>
import starData from "../assets/stars.json";
export default {
  name: "Stars",
  props: {
    starIndex: Number,
  },
  data() {
    return {
      zvezde: starData,
    };
  },
  methods: {
    // greetings() {
    //   return this.zvezde[0].line[1];
    // },
    starFun() {
      let niz = new Array(10).fill("\u00A0")
      let x = this.starIndex;
      for (let i = 1; i < 11; i++) {
        if (JSON.stringify(this.zvezde[x].line[i]) !== "{}") {
          niz[i - 1] = new Array(22).fill("\u00A0")
          let keys = Object.keys(this.zvezde[x].line[i])
          let values = Object.values(this.zvezde[x].line[i])
          for (let j = 0; j < keys.length; j++) {
            niz[i - 1][keys[j]] = values[j];
          }
        } else niz[i - 1] = new Array(22).fill("\u00A0");
      }
      let gotovNiz = niz.join("\n").toString().replace(/,/g, "\u00A0");
      return gotovNiz;
    },
  },
};
</script>

<template>
  <fieldset>
    <legend>{{ zvezde[this.starIndex].title }}</legend>
    <p>{{ starFun() }}</p>
  <br>
  <br>
  </fieldset>
</template>

<style scoped>
fieldset {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 10px;
  padding: 10px;
  width: 200px;
  aspect-ratio: 1/1;
}

legend {
  margin: 0 auto;
  font-weight: bold;
}

p {
  color: #8be9fd;
}
</style>
