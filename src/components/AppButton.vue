<script setup lang="ts">
interface AppButtonEmits {
  (event: "add-item"): void;
}
const emit = defineEmits<AppButtonEmits>();
</script>
<template>
  <div class="button-container" @click="emit('add-item')">
    <p class="button-text">Add</p>
  </div>
</template>

<style scoped lang="scss">
.button-container {
  width: 100px;
  height: 40px;
  background-color: $primary-light;
  border-radius: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  &:hover {
    cursor: pointer;
  }
  .button-text {
    color: var(--primary-text);
    font-weight: 600;
  }
}
#app[theme="light-mode"] {
  .button-container {
    background-color: $primary-lighter;
  }
}
</style>
