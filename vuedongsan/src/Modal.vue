<template>
  <div class="black-bg" v-if="modalStatus === true">
    <div class="white-bg">
      <img :src="data[selected].image" class="roomImg" alt="" />

      <h4>{{ data[selected].title }}</h4>
      <p>{{ data[selected].content }}</p>
      <!-- <button @click="modalStatus = false">닫기</button> -->
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  props: {
    selected: Number,
    modalStatus: Boolean,
    data: Array,
  },
};
</script>

<style>
</style>