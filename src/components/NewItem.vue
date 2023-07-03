<script setup lang="ts">
import AppInput from "./AppInput.vue";
import AppButton from "./AppButton.vue";
import { ref } from "vue";

interface AppButtonEmits {
  (event: "add-item", value: string): void;
}
const emit = defineEmits<AppButtonEmits>();
const itemText = ref<string>("");

function setItemText(inputText: string): void {
  itemText.value = inputText;
}
</script>

<template>
  <div class="item-container">
    <AppInput @input-changed="setItemText" />
    <AppButton @add-item="emit('add-item', itemText)" />
  </div>
</template>

<style scoped lang="scss">
.item-container {
  background-color: var(--background-4);
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
