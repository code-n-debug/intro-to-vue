// TodoItem.vue

<template>
  <div class="box">
    <article class="media">
      <div class="media-content">
        <div class="content">
          <button class="button is-danger is-small close-right" v-on:click="removeTodo">X</button>
          <div class="columns">
            <div class="column is-four-fifths">
              <h1 :class="{ 'strike' : completed}">{{name}}</h1>
              <p>{{description}}
            </div>
            <div class="column right">
              <input type="checkbox" v-on:click="completeTask" :value="completed">
            </div>
          </div>
        </div>
      </div>
    </article>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  props: ['name', 'description', 'index'],
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
  .strike{
    text-decoration: line-through;
  }

  .right{
    align-self: center;
    position: absolute;
    right: 0;
    margin-right: 40px;
  }

  .close-right{
    border-radius: 100%;
    position: absolute;
    right: 0;
    margin-top: -15px;
    margin-right: 15px;
  }
</style>