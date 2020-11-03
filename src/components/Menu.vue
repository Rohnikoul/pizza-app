<template>
  <div>
    <div class="fixed-header">
      <nav>
        <a href="#">Home</a>
        <a href="#">About</a>
        <a href="#">Products</a>
        <a href="#">Your Orders</a>
      </nav>
    </div>
  </div>
</template>

<script>

export default {
  name: "Menu",
  data() {
    return {};
  },
  props: {},
  methods: {
  },
};
</script>

<style scoped>
.fixed-header {
  width: 100%;
  position: fixed;
  background: rgb(0, 102, 167);
  padding: 10px 0;
  color: #fff;
}

.fixed-header {
  top: 0;
}

nav a {
  color: #fff;
  text-decoration: none;
  padding: 7px 25px;
  display: inline-block;
}
a:hover {
  background-color: rgb(66, 64, 62);
  color: white;
}
</style>
