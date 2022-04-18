<template>
  <div container>
    <Header />
     <Suspense>

    <Posts />
     </Suspense>
    <div class="hello">
      <h1>{{ msg }}</h1>
      <h1>{{ name }}</h1>
      <button class="btn btn-primary" v-on:click="getUser()">click me</button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue";
import Header from "./Header-Component.vue";
import Posts from './Posts-Container.vue';

// setup(()=>{
// console.log('on setup')
// })
// reactive state
const count = ref(0);

// lifecycle hooks
onMounted(() => {
  console.log("hi");
  console.log(`The initial count is ${count.value}.`);
});

export default {
  components: { Header, Posts },
  name: "HelloWorld",
  props: {
    msg: String,
  },
  // async setup() {
  //    onMounted(() => {
  //     console.log(`The initial count is ${count.value}.`);

  //   });
  // },
  data() {
    return { name: "shahab" };
  },
  methods: {
    async getUser() {
      const response = await fetch("https://gorest.co.in/public/v2/posts");
      const data = await response.json();
      console.log(data);
    },
    async getTodos() {
      const response = await fetch("https://gorest.co.in/public/v2/todos");
      const data = await response.json();
      console.log(data);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
container {
  display: flex;
  justify-content: center;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
