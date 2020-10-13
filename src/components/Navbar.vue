// TodoItem.vue

<template>
    <nav class="navbar" role="navigation" aria-label="main navigation">
      <div class="navbar-brand">
      <a class="navbar-item" href="/">
        <img style="object-fit: cover" src="https://scontent.fmnl7-1.fna.fbcdn.net/v/t1.0-1/120066424_103323658200383_1328880970847988279_n.jpg?_nc_cat=108&_nc_sid=1eb0c7&_nc_ohc=XjlgR_0R2NYAX_i1tsM&_nc_ht=scontent.fmnl7-1.fna&oh=9e8b253a52dc2e2b0f7d6aa0d0bbc660&oe=5FAA4FB3" width="112" height="28">
      </a>

      <a role="button" class="navbar-burger burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
      </div>
    </nav>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  data() {
    return {
      completed: false
    };
  },
  methods: {

  },
  mounted(){
    
  }
});
</script>

<style lang="scss" scoped>

</style>