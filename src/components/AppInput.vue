<script setup lang="ts">
import { ref, watch } from "vue";

interface AppInputProps {
  checked?: boolean;
}
interface AppInputEmits {
  (event: "input-changed", value: string): void;
}
const props = withDefaults(defineProps<AppInputProps>(), { checked: false });
const emit = defineEmits<AppInputEmits>();

const itemText = ref<string>("");

watch(itemText, () => {
  emit("input-changed", itemText.value);
});
</script>

<template>
  <div class="input-text">
    <input
      :class="{ checked: props.checked }"
      type="text"
      placeholder="Type text"
      v-model="itemText"
    />
  </div>
</template>

<style scoped lang="scss">
.input-text {
  width: 100%;
  input {
    width: calc(100% - 25px);
    font-size: $font-size-secondary-desktop;
    color: var(--primary-text);
    background-color: transparent;
    border: none;
    &.checked {
      color: var(--secondary-text);
      text-decoration: line-through;
    }
    &:focus {
      outline: none;
    }
    @media only screen and (max-width: $medium-breackpoint) {
      font-size: $font-size-secondary-mobile;
    }
  }
}
</style>
