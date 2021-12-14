<template>
  <div>
    <img :src="data.image" class="roomImg" alt="" />
    <h4>
      {{ data.title }}
    </h4>
    <p>{{ data.price }}원</p>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: {
    data: Object,
  },
};
</script>

<style>
</style>