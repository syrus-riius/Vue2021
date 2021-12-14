<template>
  <div class="menu">
    <a v-for="nav in navs" :key="nav">{{ nav }}</a>
  </div>
  <Modal
    :selected="selected"
    :modalStatus="modalStatus"
    :data="data"
    :modalClose="modalClose"
  />
  <Discount />
  <Card :data="data" v-for="(data, i) in data" :key="i" />
</template>

<script>
import data from "./assets/mock.js";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";
import Card from "./Card.vue";

export default {
  name: "App",
  data() {
    return {
      selected: 0,
      modalStatus: false,
      navs: ["Home", "Products", "About"],
      data: data,
    };
  },

  methods: {
    addReport(i) {
      this.reportCounter[i] += 1;
    },
    modalOn() {
      this.modalStatus = true;
    },
    modalClose() {
      this.modalStatus = false;
    },
  },
  components: {
    Discount,
    Modal,
    Card,
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

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.roomImg {
  width: 100%;
  margin-top: 40px;
}

body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}
</style>
