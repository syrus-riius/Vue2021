<template>
  <!-- <div v-for="(post, i) in posts" :key="i">
    <h5>post[i].title</h5>
    <p>블로그 글 날짜</p>
  </div> -->

  <div v-for="(post, i) in posts" :key="i">
    <h5>{{ post.title }}</h5>
    <p>{{ post.date }}</p>
  </div>
</template>

<script>
export default {
  name: "List",
  data() {
    return {};
  },
  props: {
    posts: Array,
  },
};
</script>

<style>
</style>