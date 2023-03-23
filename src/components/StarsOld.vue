<script>
export default {
  name: "Stars",
  data() {
    return {
      zvezdeLokal: {
        title: "ｌｕｐｕｓ",
        line1: {
          1: { 6: "✦" },
          2: { 11: "✦" },
          3: { 2: "✦" },
          4: { 8: "✦", 12: "0"},
          5: { 16: "✦" },
          6: { 11: "✦" },
          7: {},
          8: { 17: "✦" },
          9: {},
          10: { 12: "✦" },
        },
        name: "Lupus",
        quadrant: "SQ3",
        "right ascension": "15.3h",
        declination: "-45°",
        area: "333.7 sq.deg. (46th)",
        "main stars": "9",
      },
    };
  },
  methods: {
    starFun() {
      let niz = new Array(10).fill("\u00A0");
      for (let i = 1; i < 11; i++) {
        if (JSON.stringify(this.zvezdeLokal.line1[i]) !== "{}") {
          niz[i - 1] = new Array(22).fill("\u00A0");
          for (let f = 0; f < Object.keys(this.zvezdeLokal.line1[i]).length; f++) {
            niz[i - 1][Object.keys(this.zvezdeLokal.line1[i])[f]] = Object.values(this.zvezdeLokal.line1[i])[f];
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
  <legend>{{ zvezdeLokal.title }}</legend>
    <p>{{ starFun() }}</p>
  </fieldset>
</template>

<style scoped>
fieldset {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 10px;
  padding: 10px;
  width: 100px;
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
