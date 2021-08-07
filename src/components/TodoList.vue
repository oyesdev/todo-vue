<template>
  <div class="todolist">
    <div class="fixed">
      <img src="../assets/logo.png" alt="logo" class="logo" />
      <h2 class="heading">Todo List</h2>
      <form class="todo-form" v-on:submit.prevent>
        <input
          type="text"
          class="todo-input"
          v-model="todo"
          placeholder="Add items in Todo"
          @keyup.enter="addTodo"
        />
        <button @click="addTodo" type="button" class="add-btn">
          Add Item
        </button>
      </form>
      <p>{{ todo }}</p>
    </div>
    <div class="todo-item-list">
      <div v-for="(t, index) in todos" :key="t.id" class="todo-item">
        <h3>{{ t.title }}</h3>
        <i class="fas fa-trash remove-btn" @click="removeTodo(index)"></i>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      todo: "",
      idForTodo: 3,
      todos: [
        {
          id: 1,
          title: "dummy task one",
          completed: false,
        },
      ],
    };
  },
  methods: {
    addTodo() {
      if (this.todo.trim().length == 0) return;
      this.todos.push({
        id: this.idForTodo,
        title: this.todo,
        completed: false,
      });
      this.todo = "";
      this.idForTodo++;
    },
    removeTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>
<style>
.todolist {
  max-width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  overflow-y: scroll;
}

.fixed {
  position: fixed;
  min-width: 33%;
  background-color: #fff;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

.heading {
  font-size: 3rem;
}

.logo {
  display: block;
  margin: 0 auto;
  height: 5rem;
}

.todo-form {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.todo-input {
  width: 80%;
  padding: 1rem;
  font-size: 1.3rem;
  margin: 1.5rem 0;
  border: 1px solid #d3d3d3;
  border-radius: 3px;
}

.todo-input:focus {
  outline: none;
}

.add-btn {
  padding: 1rem;
  border: 1px solid #d3d3d3;
  border-radius: 3px;
  background: transparent;
  cursor: pointer;
  color: #777;
  transition: all 0.3s ease;
}

.add-btn:hover {
  color: #fff;
  background: #34495e;
}

.add-btn:focus {
  outline: none;
}

p {
  font-size: 1.3rem;
  font-weight: bold;
  padding: 0.5rem;
}

.todo-item-list {
  margin-top: 18rem;
  width: 100%;
}

.todo-item {
  width: 90%;
  padding: 0.8rem;
  border: 1px solid #d3d3d3;
  margin: 1rem auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-radius: 3px;
}

.todo-item h3 {
  color: #333;
  font-size: 1.4rem;
  font-weight: 500;
}

.remove-btn {
  font-size: 2rem;
  font-weight: 600;
  color: #aaa;
  cursor: pointer;
  transition: all 0.3s ease;
}

.remove-btn:hover {
  color: #34495e;
}

@media screen and (max-width: 1120px) {
  .fixed {
    width: 40%;
  }
}
@media screen and (max-width: 900px) {
  .fixed {
    width: 45%;
  }
}

@media screen and (max-width: 680px) {
  .fixed {
    width: 70%;
  }
}

@media screen and (max-width: 500px) {
  .fixed {
    width: 90%;
  }
}
</style>
