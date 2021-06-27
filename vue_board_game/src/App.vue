<template lang="html">
  <div id="app">
    <h1>To-Do List</h1>
    <to-do-form @todo-added="addToDo"></to-do-form>
    <ul>
      <li v-for="item in ToDoItems" v-bind:key="item.id">
        <to-do-item v-bind:label="item.label" v-bind:done="item.done" v-bind:id="item.id"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script>
import ToDoItem from './components/ToDoItem.vue';
import ToDoForm from './components/ToDoForm.vue';
export default {
  name: 'app',
  components: {
    ToDoItem,
    ToDoForm
  },
  data() {
    return {
      ToDoItems: [
        { label: 'Learn Vue', done: false},
        { label: 'Create a Vue Project with the CLI', done: true },
        { label: 'Have fun', done: true},
        { label: "Finish Simon's Assignment Before Midnight", done: false },
        { label: "Understand Vue.js enough to create a boardgame before midnight", done: false }
      ]
    };
  },
  methods: {
    addToDo() {
      console.log("To-Do Added");
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
li {
  list-style: none;
  text-align: left;
}
</style>
