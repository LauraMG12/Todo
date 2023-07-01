<script setup lang="ts">
import { ref } from "vue";

import ListItem from "./ListItem.vue";
import NewItem from "./NewItem.vue";

const items = ref([1, 2, 3, 4, 5]);
</script>

<template>
  <div class="todo-container">
    <div class="title">Title</div>
    <div class="todo-list">
      <div class="items-list">
        <ListItem v-for="item in items" :key="item" />
      </div>
      <div class="add-item">
        <NewItem />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.todo-container {
  .title {
    font-size: $font-size-primary-desktop;
    color: $dark-primary-text;
    margin: 0 10px 25px 10px;
    cursor: default;
  }
  .todo-list {
    background-color: $dark-background-2;
    border-radius: 20px;
    width: auto;
    height: calc(85vh - 180px);
    margin: 0 10px;
    padding: 25px 10px 25px 15px;

    .items-list {
      display: flex;
      flex-direction: column;
      gap: 15px;
      overflow-y: scroll;
      height: calc(100% - 80px);
      padding-right: 10px;
    }
    .add-item {
      margin-right: 15px;
      height: 80px;
      display: flex;
      align-items: flex-end;
    }
  }
}
</style>
