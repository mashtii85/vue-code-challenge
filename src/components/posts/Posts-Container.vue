<template>
  <div class="container border border-3 secondary p-2 rounded-3">
    <h2 class="text">Latest Posts</h2>
    <div class="m-3" />
    <div class="row gx-5 ">
      <div class="col-6" v-for="(post,index) in getLatest(2)" :key="post.id">
        <div class=" border border-2 rounded-2 primary bg-light" >
          <post-card class="" :index=index+1 :post="post" />
        </div>
      </div>
    </div>
  
  </div>
</template>

<script>
import PostCard from "./Post-Card.vue";
export default {
  components: { PostCard },
  name: "Posts-Container",
  created() {
    // this.posts=[]
  },
  async setup() {
    const response = await fetch("https://gorest.co.in/public/v2/posts");
    const data = await response.json();
    return { posts: data };
  },
  methods: {
    getLatest(length) {
      return this.posts.slice(this.posts.length - length);
    },
  },
};
</script>

<style scoped>
.content {
  border: 1px dashed blue;
}
.box {
  display: flex;
  justify-content: center;
  background-color: blue;
  border: 1px dashed red;
  height: 200px;
}
.text{
  text-align: left;
}
</style>
