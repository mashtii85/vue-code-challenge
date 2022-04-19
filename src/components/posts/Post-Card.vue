<template>
  <div class="d-flex flex-column justify-content-around align-items-center" style="height:200px">
      <div class="">
    <h2>Post {{ index }}</h2>
    <div >{{ post.title }}</div>
      </div>
  </div>
</template>

<script>
export default {
  name: "Post-Card",
  setup() {},
  props: {
    post: Object,
    index: Number,
  },
};
</script>

<style scoped></style>
