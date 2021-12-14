<template>
  <div class="black-bg" v-if="modalStatus === true">
    <div class="white-bg">
      <img :src="data[selected].image" class="roomImg" alt="" />

      <h4>{{ data[selected].title }}</h4>
      <p>{{ data[selected].content }}</p>
      <!-- <input @input="month = $event.target.value" /> -->
      <input v-model="month" />
      <p>{{ month }}개월 선택함 : {{ data[selected].price * month }}</p>
      <button @click="$emit('closeModal')">닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Modal",
  data() {
    return {
      month: 1,
    };
  },
  watch: {
    month(a) {
      if (a > 12) {
        alert("최대 12개월 이내로 입력하세요.");
      }
      if (isNaN(a) == true) {
        alert("문자입력하지마라");
        this.month = 1;
      }
    },
  },
  props: {
    selected: Number,
    modalStatus: Boolean,
    data: Array,
  },
};
</script>

<style>
</style>