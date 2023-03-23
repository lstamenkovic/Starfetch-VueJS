<script>
import { RouterLink, RouterView } from "vue-router";
import Header from "./components/Header.vue";
export default {
  name: "App",
  components: {
    Header,
  },
};
</script>

<template>
  <header>
    <div class="wrapper">
      <Header title="Starfetch" />
      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/list">Constellations</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div>
  </header>

  <RouterView />
</template>

<style>
* {
  text-align: center;
  color: #f8f8f2;
}
nav {
  margin: 30px;
}
nav a, button {
  text-decoration: none;
  font-size: 1.1rem;
  color: white;
  margin-left: 10px;
  border: 2px solid white;
  border-radius: 7px;
  padding: 10px;
  background: none;
}
button {
  margin: 20px 0 0 0;
}
nav a.router-link-exact-active,
nav a.router-link-exact-active:hover {
  color: #bd93f9;
  border: 2px solid #bd93f9;
}
nav a:hover,
button:hover
 {
  cursor: pointer;
  color: #ff79c6;
  border: 2px solid #ff79c6;
}
header {
  display: flex;
  justify-content: center;
}
.wrapper {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
/* RouterView { */
/*   display: flex; */
/*   flex-direction: row; */
/*   justify-content: flex-start; */
/* } */
</style>
