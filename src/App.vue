<template>
  <div>
    <todo-list v-bind:todos= "todos"></todo-list>
    <create-todo v-on:create-todo= "addTodo"></create-todo>
  </div>
</template>

<script type= "text/javascript">
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'App',
  components: {
    TodoList,
    CreateTodo,
  },
  data() {
    return {
      todos: [{
          title: 'The first thing',
          project: '1st Project',
          done: false,
        }, {
          title: 'The second thing',
          project: '2nd Project',
          done: true,
        }, {
          title: 'The third thing',
          project: '3rd Project',
          done: false,
        }, {
          title: 'The fourth thing',
          project: '4th Project',
          done: false,
        }],
    };
  },
  methods: {
    addTodo(title, project) {
      this.todos.push({
        title: title,
        project: project,
        done: false,
      });
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
