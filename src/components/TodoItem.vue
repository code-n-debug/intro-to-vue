// TodoItem.vue

<template>
  <div class="todo-item">
    <h1 :style="'text-decoration :' + (completed ? 'line-through' : '')">{{name}}</h1>
    <input type="checkbox" v-on:click="completeTask" :value="completed">
    <button v-on:click="removeTodo">Remove</button>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  props: ['name', 'index'],
  data() {
    return {
      completed: false
    };
  },
  methods: {
    completeTask(){
      this.completed = !this.completed;
    },
    removeTodo(index){
      this.$emit('onRemove', this.index);
    }
  },
  mounted(){
    console.log('My TodoItem is mounted');
  }
});
</script>

<style lang="scss" scoped>
.container {
  color: green;
}
</style>