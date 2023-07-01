<script setup lang="ts">
import AppInput from "./AppInput.vue";
</script>

<template>
  <div class="item-container">
    <div class="checked-icon">
      <img src="@/assets/unchecked.svg" />
    </div>
    <AppInput />
    <div class="close-icon">
      <img src="@/assets/cross.svg" />
    </div>
  </div>
</template>

<style scoped lang="scss">
.item-container {
  background-color: $dark-background-4;
  height: 50px;
  width: 100%;
  border-radius: 10px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  .checked-icon {
    margin: 10px 20px;
  }
  .close-icon {
    margin: 15px;
  }
  .checked-icon:hover,
  .close-icon:hover {
    cursor: pointer;
  }
}
</style>
