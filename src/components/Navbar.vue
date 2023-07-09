<script setup lang="ts">
import { useDark, useToggle } from "@vueuse/core";

const isDark = useDark({
  selector: "#app",
  attribute: "theme",
  valueDark: "dark-mode",
  valueLight: "light-mode",
});
const toggleDark = useToggle(isDark);
</script>

<template>
  <div class="navbar-container">
    <div class="logo-container">
      <img src="@/assets/todo-logo.svg" />
    </div>
    <div class="color-mode" @click="toggleDark()">
      <img v-if="isDark" src="@/assets/sun.svg" />
      <img v-else src="@/assets/moon.svg" />
    </div>
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
    background-color: var(--background-3);
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
    @media only screen and (max-width: $medium-breackpoint) {
      height: 45px;
      width: 50px;
    }
  }
}
</style>
