<template>
  <!-- TODO: 1) CREAR TABLA -->
  <div id="todos">
    <table class="container">
      <thead>
        <tr>
          <th scope="col">Id</th>
          <th scope="col">Title</th>
          <th scope="col">User Id</th>
          <th scope="col">Completed</th>
        </tr>
      </thead>
      <tbody v-for="todo in todos" :key="todo.id">
        <tr> 
          <th scope="row">{{ todo.id }}</th>
          <td>{{ todo.title }}</td>
          <td>{{ todo.userId }}</td>
          <td>{{ todo.completed }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
// TODO: 2) INSTALAR AXIOS npm install --save axios E IMPORTARLO //
import axios from "axios";

export default {
  name: "Home",
  data() {
    return {
      // TODO: 3) ALMACENAR DATOS //
      todos: null,
    };
  },

  // TODO: 5) MONTAR MÉTODO //
  mounted() {
    console.log("Hola mundo desde mounted");
    this.getTodos();
  },

  // TODO: 4) CREAR MÉTODO //
  methods: {
    getTodos() {
      console.log("aca va el codigo de get todos");

      // TODO: 6) LÓGICA API //
      axios
        .get("https://jsonplaceholder.typicode.com/todos")
        // TODO: 7) ESPERAR RESPUESTA API //
        .then((response) => {
          console.log(response);

          // TODO: 9) ASIGNAR RESPUESTA API A ALMACENAR DATOS //
          this.todos = response.data;
        })
        // TODO: 8) EN CASO DE ERROR API //
        .catch((e) => console.log(e));
    },
  },
};
</script>

<style lang="scss">
  #todos{
    text-align: center;
    border: solid 1px red;
  }
</style>
