// TodoItem.vue

<template>
    <button class="button is-danger rounded float">
        +
    </button>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style lang="scss" scoped>
    .rounded{
        border-radius: 100%;
    }

    .float{
        position: fixed;
        bottom: 0;
        right: 0;
        margin-right: 30px;
        margin-bottom: 30px;
    }
</style>