<template>
  <nav class="navbar navbar-light bg-light">
    <div class="container-fluid">
      <router-Link to="/">SYRUS</router-Link>
    </div>
  </nav>
  <router-Link to="/">Home</router-Link>
  <div></div>
  <router-Link to="/list">리스트페이지</router-Link>
  <div></div>
  <router-Link to="/detail/0">detail</router-Link>
  <router-view :posts="posts"></router-view>
</template>

<script>
import blog from "./assets/mockdata.js";

export default {
  name: "App",
  data() {
    return {
      posts: blog,
    };
  },
  components: {},
};
</script>

<style>
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
}
</style>
