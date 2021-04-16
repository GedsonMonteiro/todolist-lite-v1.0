<template>

  <div class="app">
    <ol>
      <li v-for="todo in todos" v-bind:key="todo.text"> <!-- O v-bind:key="todo.id" é para cada li ter um id unico. -->
        <p>{{ todo.text }} <button type="submit" @click="removeItem(todo.id)">Deletar</button></p> <!-- O {{ todo.text }} vai fazer o <p></p> renderizar o texto da tarefa. -->
          <span> {{ todo.id }} </span>
      </li>
    </ol>

    <div class="inputs">
      <input placeholder="Digite a tarefa" v-model="text" /> <!-- O v-model vai nos auxiliar a pegar o dado do input de adicionar tarefa, guardando em uma variavel. -->
      <div class="buttons">
        <button type="submit" v-on:click="addTodo(text)">Nova Tarefa</button> <!-- O v-on:click vai executar uma função caso o botão seja clicado. -->
        <button type="submit" v-on:click="removeTodos()">Excluir Lista</button>
      </div>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      todos: [],
      text: ''
    };
  },
  methods: {
    addTodo(text) {
      if (text !== "") {
        this.todos.push({
          id: this.todos.lenght+1,
          text,
        });
        this.text = '';
      }
    },
    removeTodos(index) {
      this.todos.splice(index, 1);
    },
    removeItem(index) {
      this.todos.splice(index, 1);
    }
  },
};
</script>

<!-- Adicione o atributo "scoped" para limitar o CSS apenas a este componente -->
<style scoped>

</style>
