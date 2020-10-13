// App.vue

<template>
  <div class="body">
    <nav-bar></nav-bar>
    <section class="section">
      <todo-item v-for="(todo, index) in todos"
        v-bind:key="index"
        v-if="!todo.completed"
        :index="index" 
        :name="todo.name | capitalize"
        :description="todo.description"
        v-on:onRemove="removeTodoItem">
      </todo-item>
    </section>
    <floating-button></floating-button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import TodoItem from './components/TodoItem.vue';
import Navbar from './components/Navbar.vue';
import FloatingButton from './components/FloatingButton.vue';

export default Vue.extend({
  filters: {
    capitalize: function (value) {
      if (!value) return ''
      value = value.toString()
      return value.charAt(0).toUpperCase() + value.slice(1)
    }
  },
  components: {
    'nav-bar' : Navbar,
    'todo-item': TodoItem,
    'floating-button': FloatingButton
  },
  data() {
    return {
      greetings: "Code and Debug TODO App!",
      name: '',
      todos: [
        {
          name: 'todo 1',
          description: 'lorem ipsumn',
          completed: false
        },
        {
          name: 'todo 2',
          description: 'lorem ipsumn',
          completed: false
        },
        {
          name: 'todo 3',
          description: 'lorem ipsumn',
          completed: false
        },
      ]
    };
  },
  methods: {
    addTodo(){
      this.todos.push({
        name: this.name
      });
      this.name = '';
    },
    removeTodoItem(index){
      this.todos = this.todos.filter((el, i)=>i!=index);
    }
  },
  mounted(){
    console.log('My App is mounted');
  }
});
</script>

<style lang="scss" scoped>

</style>