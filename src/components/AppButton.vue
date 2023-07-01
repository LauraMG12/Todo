<script setup lang="ts"></script>
<template>
  <div class="button-container">
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
    color: $dark-primary-text;
  }
}
</style>
