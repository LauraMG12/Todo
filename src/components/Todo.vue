<script setup lang="ts"></script>

<template>
  <div class="todo-container">
    <div class="title">Title</div>
    <div class="todo-list"></div>
  </div>
</template>

<style scoped lang="scss">
.todo-container {
  .title {
    font-size: $font-size-primary-desktop;
    color: $dark-primary-text;
    margin: 0 10px 25px 10px;
  }
  .todo-list {
    background-color: $dark-background-2;
    border-radius: 20px;
    width: auto;
    height: calc(85vh - 130px);
    margin: 0 10px;
  }
}
</style>
