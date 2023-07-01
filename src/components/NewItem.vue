<script setup lang="ts">
import AppInput from "./AppInput.vue";
import AppButton from "./AppButton.vue";
</script>

<template>
  <div class="item-container">
    <AppInput />
    <AppButton />
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
  padding: 0 10px 0 25px;
  @media only screen and (max-width: $medium-breackpoint) {
    background-color: transparent;
    height: 40px;
  }
  .checked-icon {
    margin: 10px 20px;
  }
  .close-icon {
    margin: 15px;
  }
}
</style>
