// App.vue

<template>
  <div class="todo">
    <div class="head">
      <h1>{{greetings}}</h1>
      <input type="text" v-model="name">
      <button v-on:click="addTodo">Add</button>
      <TodoItem v-for="(todo, index) in todos" 
        :index="index" 
        :name="todo.name" 
        v-on:onRemove="removeTodoItem">
      </TodoItem>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import TodoItem from './components/TodoItem.vue';

export default Vue.extend({
  components: {
    TodoItem
  },
  data() {
    return {
      greetings: "Code and Debug TODO App!",
      name: '',
      todos: []
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
.todo {
  display: flex;
  flex-direction: row; 
}
</style>