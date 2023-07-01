<script setup lang="ts"></script>

<template>
  <div class="navbar-container">
    <div class="logo-container">
      <img src="@/assets/todo-logo.svg" />
    </div>
    <div class="color-mode"><img src="@/assets/sun.svg" /></div>
  </div>
</template>

<style scoped lang="scss">
.navbar-container {
  max-width: 1069px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  .logo-container,
  .color-mode {
    margin: 0 20px;
  }

  .color-mode {
    height: 50px;
    border-radius: 20px;
    background-color: $dark-background-3;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 55px;
    img {
      width: 25px;
    }
    &:hover {
      cursor: pointer;
    }
  }
}
</style>
