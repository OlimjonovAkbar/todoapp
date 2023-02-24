<template>
  <div class="main mt-5 w-25 px-3 py-5 rounded-4 bg-white m-auto">
    <h1>Todo App</h1>
    <Form @addTodo="addTodo" />
    <List @onRemove="deleteTodo" @onEdit="editTodo" :todos="todos" />
  </div>
</template>

<script>
import form from "../form/form.vue";
import list from "../list/list.vue";
export default {
  components: {
    Form: form,
    List: list,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          name: "Idish yuvish",
          status: "true",
        },
        {
          id: 2,
          name: "Dars qilish",
          status: "false",
        },
        {
          id: 3,
          name: "Code yozish",
          status: "sleep",
        },
      ],
    };
  },
  methods: {
    addTodo(item) {
      const id = new Date();
      item.id = id;
      this.todos.push(item);
    },
    deleteTodo(id) {
      this.todos = this.todos.filter((val) => val.id !== id);
    },
    editTodo(id){
      const todo = this.todos.filter((val) => val.id === id);  
      console.log(todo)
    }
  },
};
</script>
<style scoped>
.main {
  height: 730px;
}
.main::-webkit-scrollbar {
  width: 0;
}
</style>
