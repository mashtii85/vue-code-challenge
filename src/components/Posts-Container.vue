<template>
  <h1>Latest Posts</h1>
  <ul>
    <li v-for="post in data" :key="post.id">{{ post.title }}</li>
    <li>hi</li>
  </ul>
</template>

<script>
import { ref } from "vue";
export default {
  name: "Posts-Container",
  async setup() {
    const posts = ref([]);
    const response = await fetch("https://gorest.co.in/public/v2/posts");
    const data = await response.json();
    posts.value = data;
    console.log(posts.value);

    return { data };
  },
};
</script>

<style scoped>
content {
  border: 1px dashed blue;
}
</style>
