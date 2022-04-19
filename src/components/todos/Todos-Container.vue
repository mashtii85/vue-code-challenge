<template>
  <div class="container bg-light border border-3 secondary p-2">
    <h2 class="text">My Todo's</h2>
    <div class="row gx-5 ">
      <div class="col-6" v-for="(todo,index) in getTodosByStatus('completed')" :key="todo.id">
        <div class=" border border-2 rounded-2 primary bg-light m-1" >
          <todo-card :index=index+1 :todo="todo" />
        </div>
      </div>
    </div>
   
  </div>
</template>

<script>

import TodoCard from "./Todo-Card.vue";
export default {
  components: { TodoCard },
  name: "Todos-Container",
  created() {
    // this.posts=[]
  },
  async setup() {
    const response = await fetch("https://gorest.co.in/public/v2/todos");
    const data = await response.json();
    return { todos: data };
  },
  methods: {
    getTodosByStatus(status) {
      return this.todos.filter(todo=>todo.status===status);
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
