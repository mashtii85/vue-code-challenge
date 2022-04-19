<template>
  <div class="container" style="max-width: 700px">
    <Header />
    <Suspense>
      <Posts />
    </Suspense>
    <Suspense>
      <Todos />
    </Suspense>

   </div>
</template>

<script>
import Header from "./Header-Component.vue";
import Todos from "./todos/Todos-Container.vue";
import Posts from './posts/Posts-Container.vue'
export default {
  components: { Header, Posts,Todos },
  name: "Home-Page",
  
};
</script>

<style scoped></style>
