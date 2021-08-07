<template>
  <div class="container">
    <TodoList />
  </div>
</template>

<script>
import TodoList from "./components/TodoList";
export default {
  components: { TodoList },
  name: "App",
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Nunito:wght@400;700&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

html {
  font-size: 62.5%; /* 1rem = 10px*/
}

::-webkit-scrollbar {
  width: 10px;
}

/* Track */
::-webkit-scrollbar-track {
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  -webkit-border-radius: 10px;
  border-radius: 10px;
}

/* Handle */
::-webkit-scrollbar-thumb {
  -webkit-border-radius: 8px;
  border-radius: 8px;
  background: #eee;
  cursor: pointer;
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.5);
}
body {
  font-family: "Nunito", sans-serif;
}
.container {
  max-width: 450px;
  height: 70vh;
  margin: 8rem auto;
  text-align: center;
  background-color: #fff;
  border: 1px solid #d3d3d3;
  border-radius: 3px;
  overflow: hidden;
}
</style>
