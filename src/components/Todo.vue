<script setup lang="ts">
import { ref } from "vue";

import ListItem from "./ListItem.vue";
import NewItem from "./NewItem.vue";

const items = ref<string[]>(["hello", "world"]);

function addItem(inputText: string): void {
  items.value.push(inputText);
  //TODO: keep items-list scroll position to bottom
}
function removeItem(index: number): void {
  items.value.splice(index, 1);
}
</script>

<template>
  <div class="todo-container">
    <div class="title">Title</div>
    <div class="todo-list">
      <div class="items-list">
        <TransitionGroup name="listItem">
          <ListItem
            v-for="(item, index) in items"
            :key="item"
            :value="item"
            @remove="removeItem(index)"
          />
        </TransitionGroup>
      </div>
      <div class="add-item">
        <NewItem @add-item="addItem" />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.todo-container {
  .title {
    font-size: $font-size-primary-desktop;
    color: var(--primary-text);
    margin: 0 10px 25px 10px;
    cursor: default;
    @media only screen and (max-width: $medium-breackpoint) {
      font-size: $font-size-primary-mobile;
      margin: 0 10px;
    }
  }
  .todo-list {
    background-color: var(--background-2);
    border-radius: 20px;
    width: auto;
    height: calc(85vh - 180px);
    margin: 0 10px;
    padding: 25px 10px 25px 15px;
    @media only screen and (max-width: $medium-breackpoint) {
      background-color: transparent;
      margin: 0;
      padding: 20px 5px 0 10px;
      height: calc(85vh - 60px);
    }

    .items-list {
      display: flex;
      flex-direction: column;
      gap: 15px;
      overflow-y: scroll;
      height: calc(100% - 80px);
      padding-right: 10px;
      @media only screen and (max-width: $medium-breackpoint) {
        gap: 10px;
        height: calc(100% - 80px);
      }
    }
    .add-item {
      margin-right: 15px;
      height: 80px;
      display: flex;
      align-items: flex-end;
      @media only screen and (max-width: $medium-breackpoint) {
        background-color: var(--background-2);
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100vw;
        height: 65px;
        align-items: center;
      }
    }
  }
}
.listItem-enter-active,
.listItem-leave-active {
  transition: all 0.5s ease;
}
.listItem-enter-from {
  opacity: 0;
  transform: translateY(30px);
}
.listItem-leave-to {
  height: 100%;
}
.listItem-leave-to {
  opacity: 0;
  height: 0;
}
</style>
