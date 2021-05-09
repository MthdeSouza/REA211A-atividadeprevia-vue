<template>
  <nav class="navbar navbar-dark bg-dark">
    <span class="navbar-brand mb-0 h1">Conversão de BitCoin por Real</span>
  </nav>
  <get-request />
</template>

<script>
import GetRequest from "./GetRequest";

export default {
  name: "App",
  components: {
    GetRequest,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
