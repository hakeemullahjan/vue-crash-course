<template>
  <div class="container">
    <div class="row">
      <div class="col-12"><p class="display-3">Vue crash course</p></div>
    </div>
    <div class="row">
      <p>Add create form</p>
    </div>
    <div class="row">
      <div class="col-12 col-lg-6">
        <ul class="list-group">
          <Todo
            v-for="(todo, index) in todos"
            :key="index"
            :todoString="todo.todoString"
            :completed="todo.completed"
          />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Todo from "./Todo";
export default {
  components: {
    Todo,
  },
  data() {
    return {
      todos: [
        { todoString: "Complete assignment", completed: false },
        { todoString: "Cook some food", completed: true },
        { todoString: "Wash car", completed: false },
        { todoString: "Feed birds", completed: true },
      ],
    };
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
