<template>
  <div id="app">
    <Menu />
    <Orders />
  </div>
</template>

<script>
import Menu from "./components/Menu.vue";
import Orders from "./components/Orders.vue";

export default {
  name: "App",
  components: {
    Menu,
    Orders,
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
  margin-top: 60px;
}
</style>
