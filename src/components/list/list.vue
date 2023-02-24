<template lang="">
  <ul class="list bg-white d-flex flex-column gap-2 pb-4 mt-5 p-0 rounded"> <listItem
  v-for="todo in todos" v-bind:todo="todo" :key='todo.id' @onEdit="$emit('onEdit',
  todo.id)" @onRemove="$emit('onRemove', todo.id)"/> </ul>
</template>

<script>
import listItem from "./listItem.vue";
export default {
  components: {
    listItem,
  },
  props: {
    todos: {
      type: Array,
      required: true,
    },
  },
};
</script>
<style scoped>
.list {
  background: #b0b0b0;
  overflow: scroll;
  height: 60%;
}

.list::-webkit-scrollbar {
  width: 0;
}

.list-item {
  padding: 10px 15px;
  background: #e4e2e2;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
