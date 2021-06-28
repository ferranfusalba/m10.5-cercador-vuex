<template>
  <div id="app">
    <div class="container">
      <h1>Cercador Vuex</h1>
      <Cerca></Cerca>
      <div class="mt-4"></div>
      <Films></Films>
      <div class="mb-4"></div>
    </div>
  </div>
</template>

<script>
import Cerca from "./components/Cerca.vue";
import Films from "./components/Films.vue";

export default {
  name: "App",
  components: {
    Cerca,
    Films,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
