<template lang="html">
  <div id="app">
    <h1>To-Do List</h1>
    <ul>
      <li v-for="item in ToDoItems" v-bind:key="item.id">
        <to-do-item label="My ToDo Item" v-bind:done="true"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script>
import ToDoItem from './components/ToDoItem.vue';
import uniqueId from 'lodash.uniqueid';
export default {
  name: 'app',
  components: {
    ToDoItem
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
</style>
