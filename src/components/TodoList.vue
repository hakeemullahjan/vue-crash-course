<template>
  <h1>TODOLIST Template</h1>
</template>

<script>
export default {
  data() {
    todos: [
      { todoString: "Complete SPM assignment", completed: false },
      { todoString: "Cook some food", completed: true },
      { todoString: "Wash car", completed: false },
      { todoString: "Feed birds", completed: true },
    ];
  },
  methods: {
    addTodo(newTodo) {
      this.todos.push({ todoString: newTodo, completed: false });
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    editTodo(todo, newTodoString) {
      todo.todoString = newTodoString;
    },
    deleteTodo(dTodo) {
      this.todos = this.todos.filter((todo) => todo !== dTodo);
    },
  },
};
</script>

<style></style>
