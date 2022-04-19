<template>
  <div
    class="d-flex flex-row bd-highlight mb-3 justify-content-around align-items-center "
    style="height: 200px"
  >
    <div class="p-2 bd-highlight p-5">
      <div class="input-group-prepend">
        <div class="input-group-text">
          <input
            type="checkbox"
            aria-label="todo status"
            disabled
          />
        </div>
      </div>
    </div>
    <div class="p-2 bd-highlight">
      <h2>Todo {{ index }}</h2>
    </div>
  </div>
</template>

<script>
export default {
  name: "Todo-Card",
  setup() {},
  created() {},
  props: {
    todo: Object,
    index: Number,
  },
 
};
</script>

<style scoped></style>
